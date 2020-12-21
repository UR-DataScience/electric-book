---
title: Video
categories: editing
order: 11
---

# Embedding video

{:.no\_toc}

* Page contents

  {:toc}

You can include any iframe in markdown to embed a video. The Electric Book template makes it especially easy to embed videos from YouTube and Vimeo:

## Setup

1. Find the video's ID. On YouTube, this is a code in the URL that looks like this: `MqlyxZiDoOA`. On Vimeo, it's a string of numbers in the URL like this: `75421736`.
2. In your markdown, use the ID:

This will embed the video like this for YouTube:

and this for Vimeo:

## Cover images

In web output, when a user is online, the HTML will automatically fetch the video cover \(aka thumbnail\) image for YouTube videos. This isn't currently possible with Vimeo.

So it's best to add an image yourself, and specify it as the cover image by adding an `image` parameter, like this:

Save the image file to your book's images folders [in the usual way](https://github.com/UR-DataScience/electric-book/tree/2a308e4940331c0bffb0ddf1cef032daccf6dc4f/_docs/images/adding-image-files.html).

## Custom classes

You can also add a class to the video to target it with custom CSS, like this:

## Descriptions

You can add a description that will appear as a caption below the video like this:

## Links

You can specify a clickable link to a video. A link is important for screen PDFs and epubs, where users need to click to see the video in their web browser or video player.

If you don't include a link, one will be generated automatically.

## Subtitles

If the video you're embedding has subtitles, you can turn them on by adding `subtitles="true"` to your include tag:

By default, the language used will be the language of the book you're editing. So, if you're editing the French translation of a book, and the video has French subtitles, those will be shown.

If you want to specify that subtitles should show in a particular language \(that the video actually supports\), then add `language="xx"`, too, where `xx` is the language code. For instance, to specify that German subtitles should show, even on an English book page:

These subtitles and language options currently only work with YouTube videos.

## Start at a specific time

You can set a video to start at a specific time by adding a `start=""` to the include tag, where you specify the number of seconds in to start. E.g. two minutes and seven seconds would be 127 seconds:

## Video options

If you want to give users other options for viewing a video, or links related to the video, you can add `options=""`, and include your options as markdown. This works in web and app outputs currently.

For example, since YouTube isn't available in some countries, you may want to provide a link to another host or a download. Remember to start markdown on a new line to avoid having indentation trigger a code block:

You can change the phrase 'Other video options' in `_data/locales.yml`.

By default, the video options do not show in PDF outputs. You can override this in your custom PDF CSS with `.video .video-options { display: block; }`.

## Legacy youtube and vimeo tags

Instead of specifying a `host=""` you can also use the host-specific tags `include youtube` or `include vimeo`. That is, instead of

## Other video services

If you're embedding from any other service, instead of using our `include` tags:

* use their standard embed iframe
* try to select a width of around 850 px
* add `style="max-width: 100%;"`
* add `class="non-printing"` to the iframe tag to hide it from PDF output.

