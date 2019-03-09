---
title: "PriNXT"
date: 2012-02-24
aliases:
  - /prinxt

tags:
- language-robot-c
categories:
- robot

description: "PriNXT was a LEGO Mindstorms NXT plotter robot that can 'print' low-resolution images onto a sheet of paper."
---

PriNXT was a LEGO Mindstorms NXT plotter robot that could "print" low-resolution images onto a sheet of paper. Check out the YouTube video I made for it below, which has **over 220,000 views**.

{{< youtube 3a1OcEXYsa0 >}}

## Hardware

PriNXT features three motors that control the machine’s main functions: two take care of the x and y axis motion for the plotter, and a third, through some pretty heavy gearing, lifts and drops the attached marker to make the dots that ended up forming the final prints. There are also several calibration sensors on board.

### Motors

PriNXT has three motors: two control the X and Y motion, and the third lifts the pen.

{{< figure src="/images/projects/2012/prinxt/bottom-view.jpg" title="An annotated bottom view of PriNXT." >}}


The first motor, the one in the middle, is very straight forward – it has two long axes coming out of it that connect to two tiny gears that can drive around on a series of gear racks, moving the contraption about the Y axis. The second and third motor are a bit more complex, since they both point inward and have to move their power around a lot.

The left one, which controls motion on the X axis, basically just gears its power to a really long row of worm wheels, which, when spun, slowly move the part that holds the pen from left to right. The third motor similarly transfers its power to the outside, after which it moves a long rod up and down, pulling the pen along with it no matter where it is.

### Sensors

The robot has a total of four sensors: two touch, one light, and one color.

{{< figure src="/images/projects/2012/prinxt/detail-view-1.jpg" title="The touch sensor was used for calibration." >}}

The touch sensors serve the simple purpose to calibrate the robot – it blindly drives towards them until it registers that they’re pressed, which tells PriNXT where to start drawing. The color sensor is used as a signal light to show that the robot has finished calibrating.</p
 
The light sensor, only added two days ago, is used for moving the pen, which has actually been one of the hardest parts of this project. Because the beam that moves the pen up and down is slightly flexible, it had to be slightly higher or lower depending on how far to the right the pen was. When the pen would move, this would cause conflicts, so now, instead of being static, the pen now continuously moves up and down a bit to compensate for this movement. The light sensor guides it in this, reading its position and telling it to either go higher or lower.

For the design part, I mostly kept this project in my usual red/ white/ shades of gray color scheme, which I’m actually starting to enjoy using more and more.

## Image processing

A big part of PriNXT was to get it to draw complex shapes and pictures like the one in the picture below.

{{< figure src="/images/projects/2012/prinxt/wilsontech.png" title="The final printed image." >}}

So this is how it works: first, I import the image into Paint.NET, where I make it black and white, and then edit it a bit to get a better looking result. Then, I export it as a .PBM file, which basically turns the whole picture into a bunch of 1’s and 0’s. Then, I import those 1’s and 0’s into NotePad++, where I reformat them to something my program will understand. Finally, I copy the results into a pre-made array in RobotC, fill in the height and width of gthe image, and I’m done!

## Programming

This is what the code for PriNXT consists of:

- Calibration functions for the X and Y motors, which basically drive them both backwards until they hit their respective touch sensors, and then reset their encoders
- A “moveLinear” function, which calculates the amount of degrees needed to get to the user specified position, and then calculates speeds for both that allow it to go there in a straight line (if one motor has to move a lot more than the other motor, the other motor slows itself down to help it keep up).
- A “movePen” function, which.. moves the pen up and down.
- A “drawBinaryImage” function, which draws the image according to the 1’s and 0’s I copy into its 2D “imageToDraw” array using two for loops, one inside the other.
- A “controlPen” task, which keeps the pen at the right height even when the “movePen” function is not called.
- The main task, which controls the rest.

You can download the program from [SourceForge here](http://sourceforge.net/projects/dimastero/files/PriNXT.c/download).

## Photo gallery

{{< figure src="/images/projects/2012/prinxt/gallery-1.jpg" >}}
{{< figure src="/images/projects/2012/prinxt/gallery-2.jpg" >}}
{{< figure src="/images/projects/2012/prinxt/gallery-3.jpg" >}}
{{< figure src="/images/projects/2012/prinxt/gallery-4.jpg" >}}
