---
title: Vision
layout: page
---

# Notes

## leading team motion and vision platforms
- team 900 zebracorn
  - hardware:
    - StereoLabs’ ZED Stereoscopic Camera
    - Custom 3D printed green LED "ring" case enclosure for camera and [Buck Boost Converter](https://www.amazon.com/DROK-Automatic-Converter-Regulator-Adjustable/dp/B00JKG57T4) to eliminate flicker
    - nVidia Jetson TX2 connected via USB
    - NavX-MXP Gyro
  - ROS w/ C++
  - images down sampled by 1/2 from 720p to reduce computational overhead

## image acquisition
- tuning of exposure and brightness to minimum settings to isolate for reflected bright LED light
- use of navx clock for timestamps shared between co-processor and roborio (avoid time sync)
  - zebracorns 2017VisionCode/zebROS ws/src/navx publisher/

## image processing

### target identification

### data calculation

- Coordinate translation between frames of reference
  - robot center x,y,z
  - camera center x,y,z
  - mounting point x,y,z
  - odometry: where robot has moved since last initialized
  - map: track robot's pose with respect to global map
- Translate target location from image based x, y, and calculated depth to real-world values:
  - distance from target
  - sideways (mis)alignment of target in relation to robot
  - vertical (mis)alignment of target in relation to robot
  - angle robot needs to turn for on target heading
  - timestamp point-in-time at which preceding data was accurate for latency compensation

### data transmission



# Resources
- 2019
  - Practical Guide to State-space Control, Tyler Veness
    - [github](https://github.com/calcmogul/state-space-guide)
    - [pdf](https://file.tavsys.net/control/state-space-guide.pdf)
  - [FRC Programming Done Right](https://frc-pdr.readthedocs.io/en/latest/)
- 2018
  - [Zebravision 6.0: A Contination of ROS for FRC](https://www.chiefdelphi.com/uploads/default/original/3X/3/3/33d306fc531cbaefc9c81aa398e4e9468515bdf7.pdf)
- 2017
  - [Zebravision 5.0: ROS for FRC](https://www.chiefdelphi.com/uploads/default/original/3X/4/e/4e66ed7b353f553d02b5526c75c9c7845b7c5cfe.pdf)
  - [github repo](https://github.com/FRC900/2017VisionCode)
- 2016
  - [Zebravision 4.0: Tracking](https://www.chiefdelphi.com/uploads/default/original/3X/d/4/d4814275333555105ffae0b6cdad72151341f061.pdf)
  - [Zebravision 4.0: Goal Detection](https://www.chiefdelphi.com/uploads/default/original/3X/0/6/065b0069b2d82c8a6f0873632cce6b426076d7eb.pdf)
  - [Zebravision 4.0: Image Capturing](https://www.chiefdelphi.com/uploads/default/original/3X/c/8/c8d8834e9595ac912c487aca3346515ab74dfe44.docx)
  - [Zebravision 4.0: Neural Networking](https://www.chiefdelphi.com/uploads/default/original/3X/8/f/8f60447285105a300ba740520a26719739a842c2.pdf)
  - Integrating Computer Vision with Motion Control, Team 254
    - [video](https://www.youtube.com/watch?v=rLwOkAJqImo&feature=youtu.be)
    - [slides](https://docs.google.com/presentation/d/1ediRsI-oR3-kwawFJZ34_ZTlQS2SDBLjZasjzZ-eXbQ/pub?start=false&loop=false&slide=id.p)
  - Taking Control of your Robot with Jared
    - [slides](https://www.team254.com/documents/control/)
- 2015
 - Motion Planning and Control in FRC
   - [video](https://www.youtube.com/watch?v=8319J1BEHwM)
   - [slides](https://www.chiefdelphi.com/uploads/default/original/3X/a/b/ab808bbf5f212c6deba8565dac83852bbd9b4394.pdf)
