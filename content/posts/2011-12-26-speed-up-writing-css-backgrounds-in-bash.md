+++
date = "2011-12-26"
layout = "post"
title = "Speed up writing CSS backgrounds in Bash"

+++

I should point out that both the original idea and implementation came from [Richard Bradshaw](http://www.bradshawenterprises.com). I highly recommend reading his [blog post](http://www.bradshawenterprises.com/blog/2011/speed-up-writing-css-backgrounds) as it's a good primer as to why this script is so useful for people who write CSS often.

**TLDR:** Getting the dimensions for background images in CSS is a common task for front end developers which requires application switching and memory work. Richard has scripted up this process which copies the resulting CSS with correct image dimensions directly to his clipboard. Schweet!

So why am I banging on about a blog post someone else has written? I thought it would be a good learning experience to port it over to Bash as the original was Python(no flame wars please). I also knew that retrieving image dimensions is trivial using imagemagick(the only pre-requisite).

{{< highlight bash >}}
#!/bin/bash

# Retrieve image dimensions using imagemagick
# We're only concerned with the first image(gifs have multiple) hence the array notation
width=`identify -format '%w' $1[0]`
height=`identify -format '%h' $1[0]`

# Build CSS string
str="background: transparent url($1) no-repeat 0 0;\n"
str+="width: ${width}px;\n"
str+="height: ${height}px;"

echo -e $str;

# Pipe out string retaining line-breaks to macosx clipboard
`echo -e $str | pbcopy`
{{< / highlight >}}

Throw the above snippet in to `/usr/bin/css-background`, make it executable and reload your terminal.

Next time you've outputted an image in Photoshop and plonked it in your images directory, give this a shot at the command line and hit paste in your editor.

{{< highlight bash >}}
$ css-background path/to/your-image.jpg

{{< / highlight >}}

Something like the following will be outputted in to your CSS file.

{{< highlight css >}}

/* Copies the following to your clipboard */
background: transparent url(path/to/your-image.jpg) no-repeat 0 0;
width: 16px;
height: 16px;

{{< / highlight >}}

Oh and Merry Christmas!
