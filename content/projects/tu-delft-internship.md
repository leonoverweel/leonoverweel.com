---
title: "TU Delft Internship"
date: 2014-07-15
aliases:
  - /tu-delft-internship

tags:
- language-c-plus-plus
- tool-robot-operating-system
- tool-qt
categories:
- robot

description: "GUI for TU Delft's 3mxl motor board that allows users to graphically edit motor parameters and share defaults across devices using XML files."
---

I spent a lot of my summer before senior year at a month-long internship at the [TU Delft Robotics Institute](http://robotics.tudelft.nl/) in Delft, the Netherlands. I got the opportunity to intern there thanks to my Science Research mentor, Guus Liqui Lung, who is Research Engineer at the university’s Biomechanical Engineering group.

The “purpose” of my internship there was for me to learn about using [ROS (Robot Operating System)](http://ros.org/). ROS is a big open source project that consists of a collection of interoperating drives, nodes and packages that allow you to add a bunch of functionality to all kinds of robots; I’m interested in ROS because I’d like to integrate the library I’ve been developing in Science Research into it (more on that soon).

{{< figure src="/images/projects/tu-delft-internship/robot.png" title="The robot on which I tested my tool." >}}

The Robotics Institute at the TU has developed a board called the 3mxl, which integrates up to 253 daisy chained motors into ROS using the Dynamixel protocol. The board keeps a 256 byte “control table” for each motor, which contains user-set parameters to make the motor behave as it should (things like the gearbox ratio, encoder resolution, motor constant, wheel diameter, spring stiffness, etc.).

This is extremely useful for abstracting away a lot of the lower level functionality, but it is kind of hard to edit, which is where the project I worked on comes in: I made an easy way for both first-time users (Minor students) and experienced users to quickly view and edit the data contained in the control table through a combination of XML files and a custom RQT-based GUI.

{{< figure src="/images/projects/tu-delft-internship/gui-1.png" title="Loading in the data." >}}

The basic premise behind my program is that it scans the 3mxl board for motors, and then, for each one it finds, reads out relevant parts of the control table (using either existing get methods, single byte reading, or bitwise shifts to combine low and high bytes for longer data types). It then applies appropriate type changes and unit conversion factors, and finally writes the parameters to both a standards-compliant XML file and to an external struct (maintained by my library) that allows both the GUI and user-made programs to access the control table data.

{{< figure src="/images/projects/tu-delft-internship/gui-2.png" title="Changing parameters." >}}

Through the GUI, the user can then edit the parameters in the struct (which was read from the current control table on the 3mxl when the XML file was generated, or imported from a GUI-made XML), and write them back to the 3mxl.

Whenever that happens, the most recent changes are used to update the XML file, which is completely portable, so a file generated on one computer-robot combination can be used to import parameters to any other computer-robot combination (provided that it has the same amount of motors, and the motors have the same IDs). All this functionality is also available as a library, so the user can, in a few lines of code, parse the XML file at the beginning of their code without having to go through the GUI.

Because of that, the user can change the parameters just by editing the XML file (by hand or through the GUI), and make changes to the control table without having to slowly write and recompile any code–particularly useful for tuning a PID algorithm, for example.

{{< figure src="/images/projects/tu-delft-internship/gui-3.png" title="Uploading parameters." >}}

Being able to import and export data between XML files and the control table also adds the advantage that someone who knows what they’re doing (e.g. my mentor) can generate a couple of standard XML files that the students can then import (and slightly tweak if necessary) and load onto their robots very easily without needing much prior knowledge.

The binaries of the two packages (the XML generation/ parsing backend and the GUI front end) are now available on TU Delft’s private SVN for Minor students to start using during the 2014 - 2015 academic year.
