---
title: Video
---

# Video

The Electric Book template includes a tag for easily inserting videos from YouTube and Vimeo. [See the docs for more](https://github.com/UR-DataScience/electric-book/tree/2a308e4940331c0bffb0ddf1cef032daccf6dc4f/samples/text/%7B%7B%20site.canonical-url%20%7D%7D/docs/editing/video.html).

In this example, we have a YouTube video, without a description, set to start 14 seconds in. There's an option to watch it elsewhere, too, which won't show on PDF by default.

{% include video id="OJWJE0x7T4Q" start="14" options=" [Watch on Bilibili](https://www.bilibili.com/video/BV1zE411X76t/)" %}

And a Vimeo one, set to start 5 seconds in.

Neither have thumbnail images specified. On the web, if an image hasn't been specified here, when you're online the page will fetch a thumbnail for YouTube videos automatically. For Vimeo and in other formats \(PDF, epub, app\), you'll get a placeholder.

Clicking the description will take you to the video online \(except in print-PDF, where the print-ready PDF's profile doesn't allow clickable links\).

