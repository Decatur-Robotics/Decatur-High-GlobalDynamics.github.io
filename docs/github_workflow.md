---
title: Github Workflow
layout: page
---

# Repository Setup

Our repository has a few permanent branches, and a few temporary ones. 
Our permanent branches are master and develop. Master is meant for working, tested robot code that’s ready to be pushed to the robot. Develop is for the latest tested code, but that may not be fully tested in a way that’s meant to be released.

Our temporary branches are mainly feature branches. These branches all follow the naming scheme “Feature-[]”, where a name of the feature is inserted in the brackets. They’re used to make new features. As an example, the branch “Feature-SimplifyRamping” is a branch made to simplify ramping.

# Development Cycle:
If there’s something that needs to be worked on, first open an issue on it. Have a descriptive name, describe the issue, give it tags, and assign it to whoever needs it. Whoever’s assigned to it should create a feature branch for it. Work on the issue, and once done create a pull request for it.

On said pull request, add relevant tags, describe what you fixed, and add some reviewers. In order to get the pull request added:

1. It’ll automatically do a build test - it needs to build without errors to be merged
1. You should get it reviewed - this usually will require testing on the robot
1. Someone with permissions needs to merge the changes
