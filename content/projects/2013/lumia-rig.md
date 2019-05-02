---
title: "Lumia Rig"
date: 2013-07-12
aliases:
  - /lumia-rig

tags:
- language-RobotC
categories:
- robot

description: "A remote-controlled LEGO Mindstorms NXT pan and tilt rig for the camera on my phone."
---

The Lumia Rig is a robot for panning and tilting a Lumia 928 Windows Phone using a remote control.

It features two degrees of freedom that can be manipulated independently, is controlled through Bluetooth via an easy to use remote, and rotates the phone exactly around where the lens is located. I’ll get into all those things individually after the video; building instructions are at the bottom of the page.

{{< youtube 74MGAOGcO7w >}}

## Hardware

The robot itself has two motors. The first moves a single small gear that spins the turntable and pans the phone. The second is a little more complex; it drives a worm wheel through the center of the turntable, which, through another series of gears, is responsible for tilting.

{{< figure src="/images/projects/2013/lumia-rig/pan.jpg" title="View of the panning motor and gearing.">}}

To get rid of the obnoxiously high amount of vibrations caused by the Mindstorms NXT motors at high speeds, the entire base rests on the rubber shock absorbers that come with the NXT set.

The remote is very minimalistic, featuring a symmetrical design with two motors on the sides that are used to input remote control data into the system, and nothing else. Both follow the red with shades of gray color scheme I’ve been using for most of my robots.

{{< figure src="/images/projects/2013/lumia-rig/remote.jpg" title="The remote control for the panning rig.">}}

## Software

The remote and the rig are both programmed in RobotC and connected via Bluetooth; three types of signals (control mode, motor A speed, motor B speed) are encoded and sent between them 33 times a second.

The “control mode” variable tells the rig what mode the remote is in: you can either control the position, where the rig quickly moves the same amount of degrees the remote control wheels are turned, or the speed, where the dials control how fast the motors use. The other two variables then tell the motors how much to move.

Because of the hardware design, if the base were to spin while the tilting motor stands still, the camera would still tilt (the gears would rotate around the worm wheel and spin themselves). To compensate for that, the remote makes sure the worm wheel is always spinning at 1/7th the speed of the panning speed; that speed is then increased or decreased to tilt. This allows for truly individual control over the different functions of the rig.

## Build your own

If you’ve got a Lumia 928 and would like to build this robot yourself, you can use the resources below.

If you have a different phone: the robot was designed to be adjustable for different sized phones fairly easily.

- Download the RobotC source code on [SourceForge](https://sourceforge.net/projects/leonoverweel/files/Lumia%20Rig/).
- Download a [PDF of the building instructions](https://skydrive.live.com/#!/view.aspx?cid=16928B5E67ACE46C&resid=16928B5E67ACE46C%214312&app=WordPdf). Note: dark red pieces aren’t the right colors; check the pictures for correct colors.
- Check it out One Mindstorm's iPhone version here (building and programming instructions available too).
- Download and resuse the raw footage from the video for free [at FCCYSF](http://www.youtube.com/playlist?list=PL5ko6Bid5lNfiAIVDslJ4ZgMtiKc6Mw0s).

## Photo gallery

{{< figure src="/images/projects/2013/lumia-rig/tilt.jpg" >}}

{{< figure src="/images/projects/2013/lumia-rig/tilt-down.jpg" >}}

{{< figure src="/images/projects/2013/lumia-rig/tilt-up.jpg" >}}
