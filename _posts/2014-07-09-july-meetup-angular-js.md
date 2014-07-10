---
layout: post
title: July Meetup &mdash; Angular JS 
categories:
- javascript
- js_frameworks
---

Yesterday we had our last CodeHub morning meetup till after the summer. I did a little workshop on Angular JS, a front-end MVC framework; mainly on the fundamentals and how to get started. - I had been wondering whether to do this at all because of a lack of expertise in this field, but I guess that is the spirit of CodeHub - and OpenTechSchool - that you can teach others something you have just learned yourself. It helps of course if there are people in the group who have worked with the technology and can add to what you are saying, and that was the case yesterday.

Rather than talking much about Angular JS itself, this is an account of some things I came across and found helpful. 

In my workshop, I basically built on two tutorials that I found particularly useful and suitable for passing on to others in a hands-on session[*](#glitches). There is Dan Wahlin's video ["AngularJS Fundamentals in 60-ish Minutes"](#wahlin) which I had first heard about from Maff Rigby at the JS workshop last year. 

The other one I came across after a - generally very helpful - discussion with Duncan Woods, who told me I should look for a tutorial that includes unit testing. It is a [two-part tutorial written by Raoni Boa Ventura](#formula1), and takes you through building a relatively simple app on top of the Angular seed project while explainig all the steps. It includes using an API as the data source and - testing! 

The interactive tutorial that [CodeSchool built with Google](#codeschool) is also quite good, from a beginner's perspective, although I think you get a better overview with the one mentioned previously. 

If you then want to dive deeper into the matter, the book to have is ["Mastering Web Application Development with AngularJS"](#mastering). Saying that, I just spotted the [ng-book](#ngbook) which looks quite comprehensive as well. 

In terms of video tutorials, I can't miss the [egghead.io](#egghead) videos of course. 

We had an interesting discussion about scaffolding tools (is that a term?) at the meetup. One thing I have noticed recently, when I have - so far for training purposes, but soon for \'real\' I hope - used various package management and build tools to bootstrap an app or website: It is immensely practical just typing in a few "npm install" or "bower install" - or just "yo angular" - and in no time have a little sample project ready that you can start from. For PHP there is composer now, but I wonder if you can ever start a PHP project with the same ease.. 

Two boilerplate tools I remember being mentioned: [mean.io](http://mean.io) (MongoDB, Express, Angular, Node), and [sailsjs.org](http://sailsjs.org/) for realtime communication. But there are so many more of course. In fact, too many, probably! I also came across an interesting post the other day that argued that we [should stop writing (and eventually using?) frameworks at all](#noframeworks)..

But even if at some point I arrived at the conclusion to *not* use a framework, I think it is good to have at least had a go at them. At the superficial level that I have progressed to now, I have to say Angular looks very good, the way it is structured makes sense to me and I found it easier to get started with it than Backbone (I didn't try very hard with that, though). But I know that once you get into the nitty-gritty it will be a lot harder, and weaknesses of the framework more apparent. I would in any case also like to try out KnockoutJS at some point.

To round this off, I\'m just going to mention two more tools. I downloaded a trial version of the [WebStorm](#webstorm) editor, and really liked how you can integrate it with Chrome to have live update in the browser. In fact I liked it in general, and am wondering whether to buy a license. Talking of Chrome, there is the [Batarang](#batarang) extension that lets you visualise scope. dependencies and performance of your app. 

I hope we can have a follow-up session on Angular at some point. And I hope that I'd soon be able to contribute to such a session, though I'd prefer it to be run by somebody else! 

### References/Resources: 

- AngularJS - [https://angularjs.org/](https://angularjs.org/)
- Angular API reference - [https://docs.angularjs.org/api](https://docs.angularjs.org/api)

- <a name="wahlin"></a>Dan Wahlin "AngularJS Fundamentals in 60-ish Minutes" - [https://www.youtube.com/watch?v=i9MHigUZKEM](https://www.youtube.com/watch?v=i9MHigUZKEM)
- <a name="formula1"></a>F1 Feeder App Tutorials by Raoni Boa Ventura - [http://www.toptal.com/angular-js/a-step-by-step-guide-to-your-first-angularjs-app](http://www.toptal.com/angular-js/a-step-by-step-guide-to-your-first-angularjs-app)
- <a name="codeschool"></a>Code School tutorial - [https://www.codeschool.com/courses/shaping-up-with-angular-js](https://www.codeschool.com/courses/shaping-up-with-angular-js)
- <a name="egghead"></a>Egghead.io Videos - [https://egghead.io/](https://egghead.io/)
- Not yet live, but looks promising (also, includes Promises) - Angular in 1h by Maff Rigby [http://maffrigby.com/learn-angularjs-in-an-hour/](http://maffrigby.com/learn-angularjs-in-an-hour/)

- Angular Seed - [https://github.com/angular/angular-seed](https://github.com/angular/angular-seed)

- <a name="mastering"></a>Book "Mastering Web Application Development with AngularJS" [http://www.packtpub.com/angularjs-web-application-development/book?tag=dp/masteringwebwithangularjs-abr1/0913](http://www.packtpub.com/angularjs-web-application-development/book?tag=dp/masteringwebwithangularjs-abr1/0913)
- <a name="ng-book"></a>Ng-Book - [https://www.ng-book.com/](https://www.ng-book.com/)

- <a name="noframeworks"></a>But hang on, perhaps we should move away from frameworks? Joe Gregorio's zero framework manifesto - [http://bitworking.org/news/2014/05/zero_framework_manifesto](http://bitworking.org/news/2014/05/zero_framework_manifesto)

- <a name="webstorm"></a>Webstorm Editor - [http://www.jetbrains.com/webstorm/](http://www.jetbrains.com/webstorm/)
- <a name="batarang"></a>Batarang Chrome extension - [https://chrome.google.com/webstore/detail/angularjs-batarang/ighdmehidhipcmcojjgiloacoafjmpfk?hl=en](https://chrome.google.com/webstore/detail/angularjs-batarang/ighdmehidhipcmcojjgiloacoafjmpfk?hl=en)
<br />&nbsp;<br />

<div style="font-size: smaller">
<a name="glitches"></a>* The session did not turn out to be as hands-on as planned though, as we faced a serious of technical glitches:<br />
- The miniport adapter to connect my laptop to screen had inexplicably broken on my way in<br />
- The wifi was not working** and for some reason we could not get any sufficient tethering either<br />
- Okay, not really technical: I had not managed to push up my files to GitHub on time, nor managed when I was at the venue; yay for memory stick keyrings..<br />

** After moving downstairs to the bar, we got Wifi working on *one* of the laptops which we then connected to the screen
</div>