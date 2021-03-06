+++
date = "2012-02-25"
layout = "post"
title = "jQuery UK conference"

+++

<img src="/images/jquery-uk.jpg" alt="jQuery UK" />

Two weeks ago I had the pleasure of going to jQuery UK in Oxford. I finally managed to write up my notes from the event, so without further ado, here they are.

### Ralph Whitbeck - The State of the jQuery Project

I enjoyed Ralph's talk, as much of what we know and love about jQuery is often taken for granted. In addition to development work and performance enhancements, it's astounding how much goes on behind the scenes in the jQuery project. Examples include maintainence of jQuery.com, the API and the CDN. I use these resources daily, and they never ever seem to experience any downtime.

Ralph also outlined what's to come in jQuery 1.8

- No new API's
- Some refactoring to bring down the file size
- Exploring ways to break IE7/8 functionality out in to a compatibility plugin
- Infrastructure overhaul
- Site refresh
- New plugin site

### Todd Parker - jQuery Mobile

This was the talk I was least looking forward to, and it turned out to be one of my favourite talks of the day. In a nutshell [jQuery Mobile](http://jquerymobile.com/) has came on leaps and bounds since it was first released, it's a million times more reliable and it boasts plenty of mobile / tablet optimised features out of the box. I look forward to working with this some time in the near future.

A few things which I found interesting:

- Touch optimized
- Hijacks links for performance reasons automatically transitions to the new page being accessed with an animation
- Testing is perfomed on actual devices rather than emulators as this yields the best results
- Utilises the HTML5 history API and gracefully degrades to to hashchange if this isn't supported by the phones browser

### Dion Almaer and Ben Galbraith - Web vs Apps

It took me a little time to get into this talk, though I wouldn't say this is a reflection on the speakers as once I caught up, I found Dion and Ben had some good stuff to say. Their underlying message is to make people realise that both of these platforms need to be leveraged appropriately depending on what's mission critical. For example mobile apps look and respond great, but it' easier to A/B test and deploy to the web frequently(no resubmission to the App Store). Whichever approach is taken, it needs to be revisited frequently to move with technical developments e.g better phones, better browsers. In doing this for Walmart Dion and Ben released a Node.js framework called [Thorax](http://walmartlabs.github.com/thorax) which looks interesting.

### Jorn Zaefferer - Pitfalls and opportunities of Single Page Web Applications

Jorn's talk was packed with useful techniques, recommended libraries and nuggets of information. Definitely the talk that I felt I got the most out of in terms of knowledge I can take away and use immediately.

Jorn managed to delve in to the topics:

- Leveraging the HTML5 history API. Notably why and how it should be used. In the event that the history API isn't supported by a users browser it should fallback gracefully to hashchange.
- Client-side error tracking. Similar to the techniques outlined in Nicholas Zakas talk on [Enterprise Error Handling](http://www.slideshare.net/nzakas/enterprise-javascript-error-handling-presentation) except at a lower level with code examples. Jorn outlined why catching JS errors in production is helpful(it pisses off users without you knowing these errors are being thrown) and how it should be done using `window.onerror` and logging this back to the server via AJAX.

### Christian Heilmann - Embracing and celebrating redundancy

I found Christian's talk highly entertaining and informative. The fact that Christian had the balls to go to Europe's first jQuery conference and advise people not to use jQuery I find hilarious. Humour aside, Christian supported his argument with many examples of why jQuery is simply not needed anymore. Browser vendors have fixed their weird inconsistencies over the past 5 years(IE9 & 10 aren't too bad at all) and implemented native API's that are very concise. He advocated that we should really determine the use case before jumping straight in to a new project and bootstrapping it with jQuery purely out of habit.

### Haymo Meran - Aloha Editor

This isn't a dig at Haymo, but I felt as an attendee that his entire talk was geared to market his product - [Aloha Editor](http://aloha-editor.org). My advice to Haymo would be to tone down on the marketing, and explain the nitty gritty of some of the cool stuff that's going on under the hood of Aloha Editor as it seems to be a well built product.

### Paul Irish - Webapp development stack & tooling

Like Christian, I found Paul's speaking style to be informative but hilarious at the same time. Paul presented a smorgasbord of high quality tools and techniques that we shold certainly keep in our toolbox when starting a new project, building a new feature or debugging code. Paul mentioned stuff like:

- JSHint
- Jade, SASS, Less, Stylus and Compass
- HAML, Markdown, Jade, Handlebars
- HTML5 boilerplate, Email boilerplate
- CoffeeScript, Dart
- Firebug, Webkit Developer Tools

As a big [SASS](http://sass-lang.com/) user, it was news to my ears to find that Paul was working on trying to get it integrated in to Google Chrome natively. Paul also showed off some awesome features in the Chrome Canary builds that are going to make my life a hell of a lot easier like JS directives.

### Addy Osmani - Large scale applications using JavaScript and jQuery

I've watched a couple of Addy's presentations online before so I found I didn't didn't get much out of this talk. It was very good don't get wrong, except I found it heavy on the theory(show me the code![]()), much in the same vein as the basis for his talk by Nicolas Zakas on Scalable JavaScript Architecture.

### Doug Neiner - Contextual jQuery

Doug's knowledge of jQuery comes through in his talks as he speaks with clearly with authority. Doug outlined why certain code styles are slow(with examples) and why it's more performant to leverage DOM traversal over ID's and classes in the right context. It's fine to keep markup clean and use complex sectors. Doug also presented that we shouldn't have all selectors running on Document Ready which I found interesting. He prefers just in time intialzation of events and selectors, as there's a chance some parts of the page won't be used that often, so why set it all up ahead of time?

To summarise, I had a fantastic time at jQuery UK (thanks [@sageuk](http://twitter.com/sageuk)), met some cool people, learnt a bit and would love to go again next year. Hats off to the folks from [White October](http://whiteoctober.co.uk) as they done a great job putting this together.
