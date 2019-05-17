---
title: "Bionic NXTPod 3.0"
date: 2011-06-12
aliases:
  - /bionic-nxtpod-3.0

tags:
- tool-LEGO-Mindstorms
categories:
- robot

description: "Inspired by Festo's Bionic Tripod 3.0, this LEGO Mindstorms NXT robot used four linear actuators to position a grabber on a flexible robot arm."
---

Bionic NXTPod 3.0 was a flexible robot arm inspired by [Festo’s Bionic Tripod 3.0](http://web.archive.org/web/20160315002745/https://www.festo.com/cms/en_corp/11371.htm). It featured four custom linear actuators that pushed four independent flexible rods up and down, making the arm able to tilt in any direction fairly quickly. A fifth motor served two functions. Controlled purely mechanically using a differential, it was able to both pump air into the pneumatics and flip the switch to open and close the top gripper.</p>

{{< figure src="/images/projects/2011/bionic-nxtpod/bionic-nxtpod.jpg" caption="Bionic NXTPod 3.0, overlaid with different arm positions." >}}

With its five motors, Bionic NXTPod 3.0 could not be controlled by a single NXT intelligent brick, which inherently only supports three motors; not being very good at BlueTooth programming back then, I had the two communicate using a light and a light sensor.

The master, on the left, would turn the height the slave’s actuators needed to go to into binary using a simple conversion function. It would then “send” this message, at ten bits per second, to the slave, which would decode it and move its motors accordingly.

There's also a YouTube video of it in action:

{{< youtube Hfwia3pJBWA youtube>}}
