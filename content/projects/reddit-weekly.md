---
title: "Reddit Weekly"
date: 2015-05-12
aliases:
  - /reddit-weekly

tags:
- api-reddit
- language-python
- language-css
- language-html
- tool-google-app-engine
categories:
- web

description: "Reddit Weekly was a site that sent customizable, weekly email digests of top posts from subreddits."
---

**Update: I've retired Reddit Weekly, and replaced it with [Weekly.Cool](https://weekly.cool), a similar service that sends you customizable reddit email digests once a week. Check it out at [https://weekly.cool](https://weekly.cool)**

There are a lot of small subreddits, especially science-y ones like [/r/EmDrive](http://reddit.com/r/emdrive) and [/r/SpaceX](http://reddit.com/r/spacex), that do not get anywhere near the volume of new post submissions that larger subreddits do — but when someone does post, it's usually something you don't want to miss. If you're subscribed to a lot of subreddits, however, there's a pretty big chance that those posts will get lost in the noise.

[Reddit Weekly](http://web.archive.org/web/20181223202651/http://reddit-weekly.appspot.com/) makes sure you don't miss out on those top posts from your favorite small subreddits by sending you weekly email updates.

{{< figure src="/images/projects/reddit-weekly/screenshot.png" title="The Reddit Weekly landing page" >}}

These updates are quick, customizable emails that are automatically delivered one morning a week, on a day that's convenient for you. All you do is specify the subreddit and the amount of content you'd like to see, and Reddit Weekly takes care of the rest. For text posts, you'll even get the post text right in the email.

The project is written in Python, and powered by [Google App Engine](https://cloud.google.com/appengine/docs) and the official [reddit API](http://www.reddit.com/dev/api).