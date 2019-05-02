---
title: "Link Syncer"
date: 2015-06-22
aliases:
  - /link-syncer

tags:
- language-Python
- language-HTML
- language-JavaScript
- language-CSS
- tool-Google-App-Engine
categories:
- web

description: "Link Syncer was a service to create quick links that will wait to redirect until everyone has clicked the Synced Link."
---

Link Syncer creates quick shareable URLs that will only redirect everyone to the link you're sharing once everyone has clicked the Synced Link.

{{< figure src="/images/projects/2015/link-syncer/landing-page.png" >}}

It's a great way to sync up with friends if you're all trying to watch a YouTube video at the same time while chatting about it, for example.

Check it out [right here](http://web.archive.org/web/20181227135009/http://link-syncer.appspot.com/)!

## How it works

First, the user pastes a link and selects how many people will join in the sync.

{{< figure src="/images/projects/2015/link-syncer/link-creation.png" >}}

Clicking "Generate!" will generate a unique Synced Link, with a prompt to click the link and then send it to others.

{{< figure src="/images/projects/2015/link-syncer/link-created.png" >}}

Once any of the users clicks the Synced Link, they see the "Waiting..." page that specifies how many people still need to click the link before everyone is redirected.

{{< figure src="/images/projects/2015/link-syncer/waiting.png" >}}

When everyone has clicked the link, the users are all redirected at the same time.

{{< figure src="/images/projects/2015/link-syncer/redirecting.png" >}}

Then, for example, you can all start watching that YouTube video at the same time!

{{< figure src="/images/projects/2015/link-syncer/result.png" >}}

## Technical stuff

This project runs on [Google App Engine](https://cloud.google.com/appengine/), Python and [Jinja2](http://jinja.pocoo.org/) on the backend, with HTML, CSS and JavaScript on the frontend. It uses the [NDB Datastore API](https://cloud.google.com/appengine/docs/python/ndb/) to store Synced Links, and the [Channel API](https://cloud.google.com/appengine/docs/python/channel/) to keep users connected once they start clicking on a Synced Link.

It took about a week to set up, and the entire codebase consists of less than 450 lines of code.
