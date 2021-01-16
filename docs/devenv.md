---
title: Developer Environment Basics
layout: page
---

The [Developer Notes](dev_notes.md) scratchpad has been moved.... 

# Synopsis: Everything coders need to git up and running for FRC 2021

Welcome coders! 

FRC Code development takes place in [the team's private repository](https://github.com/Decatur-High-GlobalDynamics/FRC-2020-Team-4026).

# Pre-requisites for contributors:
- installation of the frc 2021 developer environment w/ 3rd party libraries (this document)
- understanding of [git basics](https://docs.wpilib.org/en/stable/docs/software/basic-programming/git-getting-started.html?highlight=testing#git-version-control-introduction)
- usage of the team's [github workflow](github_workflow.md)

# DevEnv Setup and Configuration
- [WPILib Install](https://github.com/wpilibsuite/allwpilib/releases)
- Configure (global) git settings
```
    git config --global user.name "[your_github_account_name]"
    git config --global user.email "[your_github_email_address]"
    git config --global push.default current
```
- connect with team github repo maintainer, provide your github account name and request a team invite
- Clone the [code repository](https://github.com/Decatur-High-GlobalDynamics/FRC-2020-Team-4026)
<span style="display:block">![clone screenshot](/assets/images/clone.png)</span>
- Open command prompt, change to the directory where you want the repo to be, and execute...
<span style="display:block">![clone_command screenshot](/assets/images/clone_command.png)</span>
- Start WPILib installed VSCode and open the FRC-2021-Team-4026 folder  which git just created
- Install support for 3rd party libraries
  - [Cross the Road Electronics](https://docs.ctre-phoenix.com/en/latest/ch05a_CppJava.html#frc-c-java-add-phoenix)
  - [Kauai Labs navx-mxp](https://pdocs.kauailabs.com/navx-mxp/software/roborio-libraries/java/)
  - [Rev Robotics SPARK MAX]()


# Optional
- Setup ssh key authentication ([windows](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-windows)) ([linux](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-linux)) ([mac](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-mac))

# Futher Reading...
- [Github Guides][github-guides] provides a general overview of: git, github, github pages, forking projects, issues, tracking people and projects, markdown, and documentation. It should take a little less than an hour and a half to read through all of the guides.

[github-guides]: https://guides.github.com/
[git-download]: https://git-scm.com/downloads
[create-github-account]: https://github.com/join