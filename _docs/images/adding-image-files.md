---
title: Adding image files
categories: images
order: 1
---

# Adding image files

Our template comes with four folders for images, which correspond to output formats: `print-pdf`, `screen-pdf`, `web`, `epub` and `app`.

Images files must be saved there. Each folder should contain the same set of images, saved appropriately for each format. For instance, while their file names must be identical, `web` images might be full-colour, 96dpi, and up to 800 pixels wide; while `print-pdf` images might be in greyscale, 300dpi and 2400 pixels wide.

This can be a lot of work! So it's best to store large master versions of your images in the `images/_source` folder for each book and then automate their conversion to the output format folders.

For how to do this, see [Automating image conversions](https://github.com/UR-DataScience/electric-book/tree/2a308e4940331c0bffb0ddf1cef032daccf6dc4f/_docs/images/image-conversions.html).

