---
title: "Skype Car"
date: 2012-01-15
aliases:
  - /skype-car

tags:
- tool-LEGO-Mindstorms
- language-CSS
- language-HTML
categories:
- robot

description: "Skype Car was a little robotic car that hundreds of people around the world drove around my room via the web while watching a live video feed of it through Skype."
---

Skype Car was a little robotic car in a small, boxed off part of my room. Hundreds of people around the world could drive it around via the web and see a video feed of it via Skype, all in real time. Here's the YouTube video I made for it, which has <b>over 18,000 views</b>:

{{< youtube 6nVB8Us3omk youtube >}}

The process to play with Skype Car was long but not very hard. A user would go to [a web page](https://web.archive.org/web/20120113233722/http://justoverart.com/Skype%20Robot/Skype_NXT.html) and click the start button, which initiated an auto-answered Skype call with my computer. The user would then share their screen, after which they returned to the web page. Clicking the arrow keys on the site would change its background color, which, through the screenshare, was related back to my home computer screen.

{{< figure src="/images/projects/2012/skype-car/light-sensor.png" caption="The light sensor points at my computer screen and picks up colors through Skype.">}}

There, a color sensor picked it up, translated it into a message, and sent the command to the actual car via BlueTooth, which would then obey the command. For the Google Science Fair, I had different people do this, and tested how well they could complete simple tasks.

{{< figure src="/images/projects/2012/skype-car/robot-car.jpg" caption="The robot car had two individually-controlled front wheels and a back pivot ball." >}}

After a minute of inactivity, the car would use its ultrasonic distance sensor to navigate its way back to its custom wireless charging station by following the walls. _(2019 update: in hindsight, this was... dangerous.)_

{{< figure src="/images/projects/2012/skype-car/dangerous-charging.png" caption="The robot connected to its charging station by closing the exposed-wires circuit." >}}

Skype car also got some press, having been featured on  [The NXT Step](http://web.archive.org/web/20120211130420/http://thenxtstep.blogspot.com/2012/01/skype-controlled-robot-yes-you-can.html), [Engadget](http://web.archive.org/web/20160208084010/http://www.engadget.com/2012/01/10/skype-controlled-mindstorms-nxt-car-toys-over-ip/), and a german site called [Robotnews.de](http://web.archive.org/web/20130825091929/http://www.robonews.de:80/2012/02/lego-nxt-roboter-skype-steuern/).
