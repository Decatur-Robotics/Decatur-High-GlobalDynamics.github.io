---
title: NavX notes
layout: page
---

# Prerequisites
- Hardware Needed:
- Windows 10 PC
- Mini USB cable supporting Data Transfer
- NavX mxp

# NavX MXP Firmware Update
1. Go to [this site](https://pdocs.kauailabs.com/navx-mxp/software/), scroll down, and hit the large purple button that reads "Download" on the right side, then unzip the file and run setup.exe.
2. Go to [this site](https://www.st.com/en/development-tools/stsw-stm32102.html), scroll to the very last table on the site, And in the first row under download hit "Get Software"
3. Credentials for logging in are in the private FRC-2019-Team-4026 code repo in a file named '/docs/navx.secret'. 
4. If it doesn't start the download repeat step 2.
5. Unzip that folder, and run "VCP_V1.5.0_Setup_W8_x64_64bits.exe".
6. Go through the installation.
7. Go to the folder C:\Program Files (x86)\Kauai Labs\navX-MXP\navXUI, and run navXUI.exe.
8. Once it loads hit boardinfo, and record the BoardType, Board Version, and Firmware Version. My info was:
Board Version: 33
BoardType: navX-MXP
Firmware Version: 3.0.331
9. Close the navX-UI.
10. Search for and run the NavXFirmwareUpdater.
11. Unplug the NavX, then hold CAL while replugging it. You can let go of Cal when it is connected. Ensure that only the 3.3v light is on.
12. Hit "Select NavX Model firmware to load" and go to C:\Users\[Your username]\navx-mxp\firmware. Check the numbers in the hex file there against the number you recorded. There is no point in updating if they are the same or lower.
13. Select the .hex file, then hit "Update navX-Model Firmware". Wait for it to finish, and most importantly, DO NOT UNPLUG THE NAVX.
