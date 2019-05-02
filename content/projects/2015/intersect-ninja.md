---
title: "Intersect.Ninja"
date: 2015-12-28
aliases:
  - /intersect.ninja

tags:
- api-Spotify
- library-jQuery
- language-CSS
- language-HTML
- language-JavaScript
- tool-Google-App-Engine
- tool-Git
- tool-GitHub
categories:
- web

description: "Intersect.Ninja was an open source website that used the Spotify API to find intersections in the artists and tracks different people like, based on their public playlists."
---

Intersect.Ninja was an open source website that uses the Spotify Web API to find intersections in the artists and tracks different people like, based on their public playlists.

## How does Intersect.Ninja work?

When users visits [Intersect.Ninja](http://web.archive.org/web/20181108071513/http://intersect.ninja/), they're prompted to connect with their Spotify account, which starts the server-side authentication flow.</p>

{{< figure src="/images/projects/2015/intersect-ninja/landing-page.png" title="The Intersect.Ninja landing page" >}}

After authenticating, Intersect.Ninja saves the temporary access key it received from Spotify in HTML5 local storage; everything else happens client-side. From a privacy point of view, this is great since none of your data ever leaves your device.

As other users are added through the form at the top of the page, Intersect.Ninja retrieves their public playlists and crunches them to keep track of which users like which artists and tracks. It's also possible to click on a user to exclude some of their playlists from the matching process.

{{< figure src="/images/projects/2015/intersect-ninja/playlist-selection.png" title="The playlist selection interface for Intersect.Ninja." >}}

This data is displayed below the list of users, in the form of a table of artists' names, sorted first by how many users have tracks by that artist in their public playlists, then by how many tracks by the artist these users have, and then alphabetically by artist name.

Clicking an artist reveals a table that contains the tracks by that artist that are in users' public playlists, and which users like each track. The table is sorted first by how many users like the track, and then alphabetically by the track's title.

{{< figure src="/images/projects/2015/intersect-ninja/artist-detail.png" title="An artist detail page, showing which users like which of the artist's songs." >}}

That's the basic gist of the website. In the future, I'd like to add some more functionality, such as the ability to make a playlist of tracks from intersecting artists from within the interface.

## Tech Stack and Source Code

Intersect.Ninja's back end, which is responsible for authenticating with Spotify and serving up the site, runs on Python and is hosted on [Google App Engine](https://cloud.google.com/appengine/docs). The front end, which does all the computation, is a combination of JavaScript (with jQuery) and HTML/ CSS.

Intersect.Ninja is the first project I've made that's completely open source, and it's licensed under the MIT License. You can check out the source code [on GitHub](https://github.com/leonoverweel/intersect.ninja/).

There's some pretty cool stuff in there, like the sorting algorithms that are easily chainable for tie breaking, and also some stuff that could use improvement, like the way enabling / disabling some of a user's playlist is implemented.
