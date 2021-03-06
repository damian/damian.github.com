+++
title = "Project: Nearest Cineworld"
date = "2011-04-07"
+++

As an avid cinema goer, I'm always checking the [Cineworld](http://cineworld.co.uk) website to see whats showing at my local venue. Because I tend not to bookmark [anything locally](http://pinboard.in/u:damian), I get sick of having to go to their site, clicking the Cinemas tab, finding Boldon Tyne & Wear in the dropdown and so on.

Fortunately they have a nice API, around which I created a wrapper, in the form of the [cineworld gem](/posts/ruby-gem-cineworld). It also turns out I like making things for the web(kind of fitting being my day job and all). So I thought this would be an ideal opportunity to throw together a quick mashup leveraging the html5 geolocation API (which is a bit flakey btw), and some CSS3 webkit transforms to build the [Nearest Cineworld](http://nearest-cineworld.co.uk).

To get a feel for what is going on behind the scenes(massive props to [TMDb](http://www.themoviedb.org/) btw), I'm going to be open-sourcing the app, so make sure to friend me [on Github](http://github.com/damian) and keep an eye out.

[Give it a try](http://nearest-cineworld.co.uk), and let me know in the comments what you think, and more importantly if it doesn't work(which is quite likely).

**Note:** I haven't done any browser testing / graceful degredation on it, and to be fair I'm not going to.
