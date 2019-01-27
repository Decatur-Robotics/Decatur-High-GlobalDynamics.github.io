---
title: Developer Notes
layout: page
---
This could probably be split into different categories of documents...

- Shuffleboard
  - workaround for error can not find vbs script file while starting DriverStation
    - In DriverStation set "Dashboard Type" drop down menu to Shuffleboard
    - Open text editor for C:\Users\Public\Documents\FRC\FRC DS Data Storage.ini
    - Change the DashboardCmdLine to match the following:
```
    DashboardCmdLine = "wscript "C:\\Users\\Public\\frc2019\\tools\\SmartDashboard.vbs""
```

- FRC Programming General Reference
  - [FRC Programming Done Right v0.2](https://media.readthedocs.org/pdf/frc-pdr/latest/frc-pdr.pdf)
- DriverStation
  - Driver Station NI [FRC 2019 Update Suite Install](https://forums.ni.com/t5/FIRST-Robotics-Competition/FRC-2019-Update-Suite/ta-p/3861427) instructions... (Password is $Robots&in#SPACE!!)
- Git
  - [Free Git book (pdf)](https://git-scm.com/book/en/v2)
  - [Recommended global configuration to enable creating remote branches][git-default-config-remote-branch]

        git config --global push.default current

- Gradle
  - How to [configure build.gradle to show unchecked warnings and deprecations][make-gradle-show-warnings]. Add the following to build.gradle:

        compileJava {
            options.encoding = 'UTF-8'
            options.compilerArgs << "-Xlint:unchecked" << "-Xlint:deprecation"
        }
        
        compileTestJava {
            options.encoding = 'UTF-8'
            options.compilerArgs << "-Xlint:unchecked" << "-Xlint:deprecation"
        }
- Checkstyle
    - You can work on [Checkstyle](http://checkstyle.sourceforge.net/index.html) configurations by reading the [Extending Checkstyle Section](http://checkstyle.sourceforge.net/extending.html).

- Scouting
  - [Our scouting app (based on team 2102's)][team4026-roborecon-app-repo]
- [WPILib Documentation][wpilib-docs]
- [Commands & Subsystems][commands-and-subsystems]
- Youtube Videos
  - [Playlist of East Robotics’s Excellent YouTube Tutorials][east-robotics-youtube-playlist]
    - [Setup][east-robotics-video-setup] (not the most useful)
    - [Drivebase][east-robotics-video-drivebase] (Good)
    - [TankControl Setup][east-robotics-video-tank-control] (Good)
    - [Talon SRX (CAM bus)][east-robotics-video-talon-srx] (Probably not useful)
    - [Version Control (git)][east-robotics-version-control-git]
    - [PID Tutorial][east-robotics-pid-controller] (Very Good)
- [Official FRC-programming webinar][frc-programming-webinar] (does not cover Command/Subsystem)
- FRC Command/Subsystem YouTube tutorial by Rudyard Robotics (Slightly Painful, Slightly Useful)
  - [Video1][rudyard-robotics-video-1]
  - [Video2][rudyard-robotics-video-2]
- Pixy Camera, just FYI
- [DroneBot-Helpful but slow walkthrough][dronebot-walkthrough-video]
- [siSTEM sharing Pixy2 experience][sistem-sharing-pixy2] [FTC only]


# Notes on Importing old project
- Launched VSCode
- Open Command Palette
- Command Palette can be accessed from the View menu or by pressing Ctrl+Shift+P (Cmd+Shift+P on Mac).
- WPILib import eclipse project
- [Import Talon SRX Library][ctre-talon-srx-resources] v5.12.1.0.zip
- Add Talon SRX Library to VSCode
- 55% (“Step 19” “Add CTRE Libraries”) from this document
- Connect to robot
- Command Palatte: “WPILib Build Robot Code”

## Old Alpha notes on setting up dev env

# VS Code Setup
- [FRC Plugin Install Guide](https://wpilib.screenstepslive.com/s/currentCS/a/932382-installing-visual-studio-code-c-java)
- [WPILib](https://github.com/wpilibsuite/vscode-wpilib)
- [WPILib 2](https://wpilib.screenstepslive.com/s/currentCS/m/java/l/1027060-visual-studio-code-basics-and-the-wpilib-extension)
- [Setup WPILib Project](https://wpilib.screenstepslive.com/s/currentCS/m/java/l/1027062-creating-a-robot-program)

# Setting Up Driver Station and RoboRIO
- [Instruction Manual Update Suite](https://forums.ni.com/t5/FIRST-Robotics-Competition/FRC-2019-Update-Suite/ta-p/3861427)
- [Known issue with Driver Station](https://github.com/wpilibsuite/allwpilib/issues/1532)

# 2018 Code Update
- [WPILib API](http://first.wpi.edu/FRC/roborio/release/docs/java/)
- [WPILib Plugin Changelog](https://wpilib.screenstepslive.com/s/currentCS/m/java/l/837061-c-java-plugin-changelog)

# Coding Standards
- [Java](https://docs.google.com/document/d/1dtUXsO5NYfXWg4fBMzcRnjsHshb5kiMHxoAjeThrsic/edit)

# Raspberry Pi
- [Vision](http://wpilib.screenstepslive.com/s/currentCS/m/85074)

# Contributing to WPILib
- [2018 Developer Presentation](https://cpb-us-w2.wpmucdn.com/wp.wpi.edu/dist/1/35/files/2018/05/Building-and-Contributing-to-WPILib-2018.pdf)

[gradle-warnings-deprecations]: https://stackoverflow.com/questions/18689365/how-to-add-xlintunchecked-to-my-android-gradle-based-project
[wpilib-docs]: https://wpilib.screenstepslive.com/s/currentCS
[commands-and-subsystems]: https://wpilib.screenstepslive.com/s/currentCS/m/java/c/88893
[east-robotics-youtube-playlist]: https://www.youtube.com/playlist?list=PLUSdSy9CkwBIiISFMa_ThWmtFCKtYLUE_
[east-robotics-video-setup]: https://www.youtube.com/watch?v=b3buDnD8vWc&t=8s&list=PLUSdSy9CkwBIiISFMa_ThWmtFCKtYLUE_&index=2
[east-robotics-video-drivebase]: https://www.youtube.com/watch?v=vz_C-LqmTJA&t=0s&list=PLUSdSy9CkwBIiISFMa_ThWmtFCKtYLUE_&index=3
[east-robotics-video-tank-control]: https://www.youtube.com/watch?v=herfqqjAiM0&t=0s&list=PLUSdSy9CkwBIiISFMa_ThWmtFCKtYLUE_&index=4
[east-robotics-video-talon-srx]: https://www.youtube.com/watch?v=gqfiysI20ZY&t=0s&list=PLUSdSy9CkwBIiISFMa_ThWmtFCKtYLUE_&index=5
[east-robotics-version-control-git]: https://www.youtube.com/watch?v=boeCjJKg-LY&t=129s&list=PLUSdSy9CkwBIiISFMa_ThWmtFCKtYLUE_&index=6
[east-robotics-pid-controller]: https://www.youtube.com/watch?v=_mKlRbapkXo
[frc-programming-webinar]: https://www.youtube.com/watch?v=tR8wtXd2Ack
[rudyard-robotics-video-1]: https://www.youtube.com/watch?v=t-otjytqzCw
[rudyard-robotics-video-2]: https://www.youtube.com/watch?v=t-otjytqzCw
[dronebot-walkthrough-video]: https://www.youtube.com/watch?v=391dXDjqzXA
[sistem-sharing-pixy2]: https://www.youtube.com/watch?v=YWBXLoB47is&t=7s
[ctre-talon-srx-resources]: http://www.ctr-electronics.com/control-system/hro.html#product_tabs_technical_resources
[team4026-roborecon-app-repo]: https://github.com/Decatur-High-GlobalDynamics/roborecon-app
[make-gradle-show-warnings]: https://stackoverflow.com/questions/18689365/how-to-add-xlintunchecked-to-my-android-gradle-based-project
[git-default-config-remote-branch]: https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch/27185855#27185855
