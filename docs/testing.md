---
title: Testing and Simulation Notes for FRC 2021
layout: page
---

# Priorities and Goals

1. Avoid going backwards
2. Enable software development to progress when access to robots, driver stations, etc. is limited
3. Manage complexity (without adding much)

# Types of Software Testing

- Unit Testing: testing components in isolation
- Integration Testing: testing interfaces/glue between components

# Changes required to devenv and code

- Note: Gradle builds will automatically run tests and fail on test failure
- Updates to build.gradle: add repositories and mockito dependency

```yaml
repositories {
    mavenCentral()
    mavenLocal()
    jcenter()
    flatDir {
            // The directory lib is available as a source for dependencies - we put any JAR files here
            // The directory lib will always be one folder "above" a subproject folder - thus the ".."
            dirs '../lib'
        }
    maven { url 'https://jitpack.io' }
}
```

```yaml
dependencies {
    [...]
    testImplementation 'org.mockito:mockito-core:2.+'
    [...]
}
```
- Refactor subsystems to decouple subsystem constructor from hardware instances

  - To allow mocking and testing the tight coupling of instantiating new instances of hardware objects within the subsystem constructor needs to be refactored so that the subsystem constructor takes those object instances as parameters. This will allow tests to inject mocked dependencies into the subsystem. I.e. allowing the tests to run without actual hardware being present. 
  
  - For example refactor ClimberSubsystem from

```java
public class ClimberSubsystem extends SubsystemBase {
  private final WPI_VictorSPX leftClimber;
  private final WPI_TalonSRX rightClimber;
  private final DigitalInput leftLimit;
  private final DigitalInput rightLimit;
  private final DigitalInput leftHookLimit;
  private final DigitalInput rightHookLimit;

  public ClimberSubsystem() {
    leftClimber = new WPI_VictorSPX(Constants.LeftClimbCAN);
    rightClimber = new WPI_TalonSRX(Constants.RightClimbCAN);
    leftLimit = new DigitalInput(Constants.Climber_LeftLimitDIO);
    rightLimit = new DigitalInput(Constants.Climber_RightLimitDIO);
    rightHookLimit = new DigitalInput(Constants.Hook_RightDIO);
    leftHookLimit = new DigitalInput(Constants.Hook_LeftDIO);
  }

  ...
```

to

```java
public class ClimberSubsystem extends SubsystemBase {
  private WPI_VictorSPX leftClimber;
  private WPI_TalonSRX rightClimber;
  private DigitalInput leftLimit;
  private DigitalInput rightLimit;
  private DigitalInput leftHookLimit;
  private DigitalInput rightHookLimit;

  // constructor
  // decouple external dependencies to allow dependency injection for testing
  public ClimberSubsystem(
    WPI_VictorSPX leftClimber, WPI_TalonSRX rightClimber,
    DigitalInput leftLimit, DigitalInput rightLimit,
    DigitalInput leftHookLimit, DigitalInput rightHookLimit
  ) {
    this.leftClimber = leftClimber;
    this.rightClimber = rightClimber;
    this.leftLimit = leftLimit;
    this.rightLimit = rightLimit;
    this.rightHookLimit = rightHookLimit;
    this.leftHookLimit = leftHookLimit;
  }

  // ClimberSubsystem Factory
  public static ClimberSubsystem Create() {
    WPI_VictorSPX leftClimber = new WPI_VictorSPX(Constants.LeftClimbCAN);
    WPI_TalonSRX rightClimber = new WPI_TalonSRX(Constants.RightClimbCAN);
    DigitalInput leftLimit = new DigitalInput(Constants.Climber_LeftLimitDIO);
    DigitalInput rightLimit = new DigitalInput(Constants.Climber_RightLimitDIO);
    DigitalInput rightHookLimit = new DigitalInput(Constants.Hook_RightDIO);
    DigitalInput leftHookLimit = new DigitalInput(Constants.Hook_LeftDIO);
    return new ClimberSubsystem(leftClimber, rightClimber, leftLimit, rightLimit, leftHookLimit, rightHookLimit);
  }
  
  ...
```

and refactor all code which creates instances of the ClimberSubsystem from:

```java
public class RobotContainer {
  ...
  private ClimberSubsystem climber = new ClimberSubsystem();
```

to

```java
public class RobotContainer {
  ...
  private ClimberSubsystem climber = ClimberSubsystem.Create();
```

## Creating Unit Tests

Create new tests in a mirrored test directory structure using [original classname] + Test.java.

[./src/test/java/frc/robot/subsystem/ClimberSubsystemTest.java]

```java
package frc.robot.subsystems;

import com.ctre.phoenix.motorcontrol.can.WPI_TalonSRX;
import com.ctre.phoenix.motorcontrol.can.WPI_VictorSPX;
import edu.wpi.first.wpilibj.*;

import org.junit.*;
import static org.mockito.Mockito.*;

public class ClimberSubsystemTest {

  @Test
  public void stopMeansStop() {

    // Assemble
    WPI_VictorSPX leftClimber = mock(WPI_VictorSPX.class);
    WPI_TalonSRX rightClimber = mock(WPI_TalonSRX.class);
    DigitalInput leftLimit = mock(DigitalInput.class);
    DigitalInput rightLimit = mock(DigitalInput.class);
    DigitalInput rightHookLimit = mock(DigitalInput.class);
    DigitalInput leftHookLimit = mock(DigitalInput.class);

    ClimberSubsystem climber =
        new ClimberSubsystem(
            leftClimber, rightClimber, leftLimit, rightLimit, leftHookLimit, rightHookLimit);

    // Act
    climber.stop();

    // Assert
    verify(leftClimber, times(1)).set(0);
    verify(rightClimber, times(1)).set(0);
  }
}
```