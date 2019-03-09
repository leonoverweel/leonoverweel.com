---
title: "Mugsy Website"
date: 2015-05-18
aliases:
  - /mugsy-website

tags:
- language-python
- language-html
- language-css
- language-javascript
- tool-google-app-engine
categories:
- web

description: "For my Rye High School senior year internship, I worked with Sean Reilly of Mugsy to build him a new company website."
---

Rye High School has a senior internship program, where the senior class spends the last few weeks of school (after APs end) working different jobs. I worked at Mugsy, a New York City-based production company run by Sean Reilly; most of my work consisted of building the website presented on this page. You can see it live [here](http://mugsy.tv/).

{{< figure src="/images/projects/2015/mugsy-website/homepage.png" >}}

The website consists of a few static files like a landing page, an about page (see screenshot below), and a contact page, but the rest is all dynamically generated. Of course, the website is also completely adaptive to different screen sizes, and will change its layout depending on whether it is viewed on a desktop, laptop, tablet, or smartphone.

{{< figure src="/images/projects/2015/mugsy-website/about.png" >}}

One of the requirements of the website was to showcase the different directors and editors Sean works with, so I had to build a custom Content Management System to keep track of a bunch of information about the different people involved with the company. All the data in this system is managed from a custom admin panel (see screenshot below).

{{< figure src="/images/projects/2015/mugsy-website/cms.png" >}}

As usual, this system runs on Google App Engine, and data is stored in GAE's New Database (NDB). Each person to be showcased on the website get either a "director" or "editor" role, and a skill set, description, and portfolio.

Every time such a person is added or any information regarding a person is changed, the Python code takes care of re-rendering the HTML for the pages that list the different directors and editors (see screenshot below), and the actual pages about these people.

{{< figure src="/images/projects/2015/mugsy-website/directors.png" >}}

The pages for each person contain their name, skill set, a description, and a portfolio of their work (see screenshot below). Mugsy hosts its media on [Simian](http://www.gosimian.com/), and Sean can add a video to a person's portfolio by pasting Simian's default embed code on the admin page. The back end then takes care of extracting the video ID and generating a customized JavaScript-resizable embed that allows the page to dynamically resize the video depending on the device's screen size.

{{< figure src="/images/projects/2015/mugsy-website/kauffman.png" >}}

The website took about a month to put together, and it was a great learning experience figuring out how to make my own Content Management System (I actually reused a lot of it to build this personal portfolio website).