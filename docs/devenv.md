---
title: Developer Environment Basics
layout: page
---

The [Developer Notes](/docs/dev_notes.md) scratchpad has been moved.... 

# Synopsis: Everything coders need to git up and running for FRC 2019

Welcome coders! 

FRC 2019 Code development takes place in [the team's private repository][team4026-frc2019-repo].

# Pre-requisites for contributors:
- installation of the frc 2019 developer environment w/ talon srx add-on support (this document)
- understanding of [git basics](/docs/git_basics.md)
- usage of the team's github workflow
- complete the hello world exercise to demonstrate mastery of the basics (TODO)

# DevEnv Setup and Configuration

- [Installing C++ and Java Development Tools for FRC][1027503-installing-c-and-java-development-tools-for-frc]
  - Ubuntu linux developers should read and follow [these linux specific notes][frc2019-vscode-and-3rd-party-install]. make sure you read the replies and comments.
  - Windows developers need to make sure you:
    - manually "click Select/Download VSCode" when running the installer
    - [download and install git][git-download]
- [Setup a personal github account][create-github-account]
- Configure (global) git settings
```
    git config --global user.name "[your_github_account_name]"
    git config --global user.email "[your_github_email_address]"
    git config --global push.default current
```
- Email our team github org maintainer (Aaron) to request a team invite
- Clone the [code repository][team4026-frc2019-repo] and add yourself to /COMMITTERS.txt (Note you will not have access to the code repository until after you have requested, recieved, and accepted an invite from the team's github organization.)

# Optional

- Setup ssh key authentication ([windows](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-windows)) ([linux](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-linux)) ([mac](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-mac))

# Futher Reading...

- [Github Guides][github-guides] provides a general overview of: git, github, github pages, forking projects, issues, tracking people and projects, markdown, and documentation. It should take a little less than an hour and a half to read through all of the guides.

[github-guides]: https://guides.github.com/
[team4026-frc2019-repo]: https://github.com/Decatur-High-GlobalDynamics/FRC-2019-Team-4026
[1027503-installing-c-and-java-development-tools-for-frc]: https://wpilib.screenstepslive.com/s/currentCS/m/java/l/1027503-installing-c-and-java-development-tools-for-frc
[frc2019-vscode-and-3rd-party-install]: https://www.chiefdelphi.com/t/installation-of-the-2019-vscode-and-third-party-libraries-on-ubuntu/340789
[git-download]: https://git-scm.com/downloads
[create-github-account]: https://github.com/join