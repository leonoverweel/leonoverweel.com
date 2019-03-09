---
title: "Science Olympiad Robot"
date: 2013-12-15
aliases:
  - /science-olympiad-robot

tags:
- language-robot-c
categories:
- robot

description: "For the Robot Arm challenge of our local Science Olympiad, my friend and I built an arm featuring four controllable DOMs."
---

In our local 2013 Science Olympiad, my friend Michael Chen and I did the Robot Arm challenge and ended up doing pretty well, finishing in 7th place.

{{< figure src="/images/projects/2013/science-olympiad/robot-arm-1.jpg" >}}

Our arm featured four controllable DOMs: the base rotated, the arm moved at two joints, and the gripper opened and closed. Although it wasn’t driven by any motors, the gripper itself moved too, always keeping itself vertical assisted by gravity.

It was controlled using a Surface Pro running RobotC, connected to the base via USB cable. On the Surface, the interface was fairly simple: the up and down arrow keys shifted which of the robot’s functions was being controlled, while the left and right arrow keys actually moved the selected function. The NXT brick connected to the computer relayed its commands to the second NXT brick via Bluetooth. The code for the master NXT is [available here](http://sourceforge.net/projects/leonoverweel/files/SciOlyRobotArm13.c/download) and the code for the slave NXT is [available here](http://sourceforge.net/projects/leonoverweel/files/SciOlyRobotArm13Slave.c/download).

## Photo gallery

{{< figure src="/images/projects/2013/science-olympiad/robot-arm-2.png" >}}
{{< figure src="/images/projects/2013/science-olympiad/robot-arm-3.png" >}}
{{< figure src="/images/projects/2013/science-olympiad/robot-arm-4.png" >}}
{{< figure src="/images/projects/2013/science-olympiad/robot-arm-5.png" >}}
{{< figure src="/images/projects/2013/science-olympiad/robot-arm-6.png" >}}
