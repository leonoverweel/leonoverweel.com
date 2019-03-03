---
title: "Flyer Robot"
date: 2013-06-25
aliases:
  - /flyer-robot

tags:
- language-robot-c
categories:
- robot

description: "For our annual Science Research symposium, I built a demo robot arm to hand out flyers to the audience."
---

For my Science Research presentation sophomore year, I built a demo robot to hand out the flyers/ programs to the people who came by. See the video I made of it below:

{{< youtube p7zqB6b_CgY >}}

Device-wise, the robot consists of the following functional parts:

- 2 Mindstorms NXT Intelligent Bricks (1.0 & 2.0)
- 2 100mm Firgelli Linear Actuators
- 2 Mindstorms NXT Motors
- 1 LEGO Technic Small Motor
- 4 Mindsensors Flexi-Cables for NXT (1 meter long & 1.5 meters long)
- 1 Custom-made NXT-Technic Motor cable
- 3 Touch Sensors
- 1 Ultrasonic Sensor

## How it works

After the Ultrasonic Sensor registers a new visitor, the Master NXT (“Jeeves”) sends a Bluetooth signal to the Slave NXT (“Alfred”), which would then turn four wheels that push the bottom program into the arm’s gripper.

{{< figure src="/images/projects/flyer-robot/flyer-dispenser.jpg" >}}

Then, Alfred closes the gripper to grab the program once its pushed forward enough to hit a touch sensor (that in-focus gray axle extends into the sensor.)

{{< figure src="/images/projects/flyer-robot/gripper.jpg" >}}

Once a Bluetooth signal is sent back when Alfred finishes, Jeeves uses the Linear Actuators to move the flyer to the desired position.

{{< figure src="/images/projects/flyer-robot/linear-actuators.jpg" >}}

A second joint, also controlled by Jeeves, assists in handing out the flyer.

{{< figure src="/images/projects/flyer-robot/second-joint.jpg" >}}

Finally, Jeeves once again signals Alfred to let go of the program, and the arm returns to its default position, assisted by two more touch sensors used to calibrate different parts of the arm.

{{< figure src="/images/projects/flyer-robot/closed-configuration.jpg" >}}

Originally, I’d also planned to use an IMU to measure when the visitor grabs a program and only let go of it then; due to time constraints, however, I decided to just use a two second timer. The arm itself, as you can see in the video, is pretty shaky too, so it would have been hard to filter out those vibrations from those caused by a potential visitor grabbing the program.

## Photo gallery

{{< figure src="/images/projects/flyer-robot/open-configuration.jpg" >}}
