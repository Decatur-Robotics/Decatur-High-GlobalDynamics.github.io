---
title: Developer Notes
layout: page
---

# General Resources
- Git [Free Git book (pdf)](https://git-scm.com/book/en/v2)
- [WPILib Documentation](https://docs.wpilib.org/en/stable/)

# Annual Updates
- [WPILib Install](https://github.com/wpilibsuite/allwpilib/releases)
- [Installing FRC Game Tools](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/frc-game-tools.html) (Labview Update, FRC Driver Station, and FRC Utilities) 
- [Imaging your roboRIO](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/imaging-your-roborio.html)
- [FRC Radio Configuration](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/radio-programming.html)
- [CTRE Phoenix Framework and Pigeon Tuner](https://github.com/CrossTheRoadElec/Phoenix-Releases/releases)
- [CTRE Falcon 500](http://www.ctr-electronics.com/talon-fx.html#product_tabs_technical_resources)
- [CTRE Talon SRX](http://www.ctr-electronics.com/talon-srx.html#product_tabs_technical_resources)
- [CTRE Victor SPX](http://www.ctr-electronics.com/victor-spx.html#product_tabs_technical_resources)
- SPARK MAX
  - [software resources](https://www.revrobotics.com/sparkmax-software/)
  - [firmware update](https://docs.revrobotics.com/sparkmax/software-resources/spark-max-firmware-change-log)
  - 3rd party libraries installation
    - [java](https://docs.revrobotics.com/sparkmax/software-resources/spark-max-api-information#java-api)
    - [cpp](https://docs.revrobotics.com/sparkmax/software-resources/spark-max-api-information#c-api)
  - [videos](https://www.youtube.com/revrobotics)
- Kauai Labs navx-mxp
  - [official firmware upgrade instructions](https://www.kauailabs.com/support/navx-mxp/kb/faq.php?id=48)
  - [Keon's Notes from prior years](navx.md)
  - [navXUI](https://pdocs.kauailabs.com/navx-mxp/software/navx-mxp-ui/)

# Miscellaneous
- Shuffleboard
  - workaround for error can not find vbs script file while starting DriverStation
    - In DriverStation set "Dashboard Type" drop down menu to Shuffleboard
    - Open text editor for C:\Users\Public\Documents\FRC\FRC DS Data Storage.ini
    - Change the DashboardCmdLine to match the following:
```
    DashboardCmdLine = "wscript "C:\\Users\\Public\\frc2019\\tools\\SmartDashboard.vbs""
```
- Gradle
  - How to [configure build.gradle to show unchecked warnings and deprecations](https://stackoverflow.com/questions/18689365/how-to-add-xlintunchecked-to-my-android-gradle-based-project). Add the following to build.gradle:

        compileJava {
            options.encoding = 'UTF-8'
            options.compilerArgs << "-Xlint:unchecked" << "-Xlint:deprecation"
        }
        
        compileTestJava {
            options.encoding = 'UTF-8'
            options.compilerArgs << "-Xlint:unchecked" << "-Xlint:deprecation"
        }
- Checkstyle
    - Download Checkstyle by pressing `CTRL + Shift + X` in VSCode and typing in `CheckStyle for Java`
    - You can work on [Checkstyle](http://checkstyle.sourceforge.net/index.html) configurations by reading the [Extending Checkstyle Section](http://checkstyle.sourceforge.net/extending.html).


# Coding Standards
- [Java](https://docs.google.com/document/d/1dtUXsO5NYfXWg4fBMzcRnjsHshb5kiMHxoAjeThrsic/edit)


# Contributing to WPILib
- [2018 Developer Presentation](https://cpb-us-w2.wpmucdn.com/wp.wpi.edu/dist/1/35/files/2018/05/Building-and-Contributing-to-WPILib-2018.pdf)
