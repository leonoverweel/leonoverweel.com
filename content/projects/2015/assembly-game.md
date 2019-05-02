---
title: "Assembly Game"
date: 2015-10-20
aliases:
  - assembly-game

tags:
- language-Assembly

description: "For TI1406 lab, I made an Assembly game much like Arc Spin, along with a few other cool projects."
---

One of my first-quarter classes at [Delft University of Technology](http://tudelft.nl/) was TI1406, Computer Organization, taught by [Dr. Alexandru Iosup](http://www.pds.ewi.tudelft.nl/~iosup/) and [Otto Visser](http://www.st.ewi.tudelft.nl/~visser/).

The lab component of this course consisted of learning and programming in the [x86-64 assembly language](https://en.wikipedia.org/wiki/X86_assembly_language). There were a few simple required assignments like calculating a number raised to another number and recursively calculating a factorial, but the more interesting projects were the four optional ones. My lab partner Daniël Vos decided to divide and conquer, and did all of them.

One of the projects I did was assignment 8: using assembly to implement a game. Much inspired by [Arc Spin](http://leonoverweel.com/arc-spin), the point of the game is to keep moving as long as you can without hitting the moving obstacles. Here's a video demo of it running in a Debian virtual machine:

{{< youtube X8D0pkEJID8 >}}

The players have to make sure their character does not hit the blue bars moving across the screen or the yellow bar at the top. They do so by moving their character down (by pressing _q_ for player 1 and _p_ for player 2), while the playing field continuously moves up faster and faster as the game progresses.

A player wins when the other player's character hits a blue obstacle or the top of the screen; when this happens, the game pauses so the losing player can see what obstacle his character hit. After a second, the winning player will see her score (at the top of the screen) increase by one, and the game starts over.

{{< figure src="/images/projects/2015/assembly-game/screenshot.png" >}}

The game took about 20 hours to make (all in one day — as the deadline approached, Daniël and I stayed up for 38 hours finishing everything), and is made using around 520 lines of AT&T-syntax x86-64 assembly code. Maurice Bos and Maarten de Vries are the authors of the game library it is built on.

I also made a [Brainfuck](https://en.wikipedia.org/wiki/Brainfuck) interpreter for another assignment, and Daniël and I worked together on making a program that created a [SHA-1](https://en.wikipedia.org/wiki/SHA-1) hash of some input ASCII text. Overall, the lab was super fun and Assembly, frustrating as it can be, will always have a special place in my hea_Segmentation Fault_