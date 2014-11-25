---
layout: post
title: JavaScript 1-day workshop, September 2014
author: Katja 
categories:
- javascript
- mean_stack
- js_frameworks
- rest_api
- node
- express
- mongo
- maps
---

On the 13th of September, CodeHub hosted a [day-long JavaScript event](http://www.meetup.com/CodeHub-Bristol/events/196402012/) at the YHA in Bristol, which consisted of 7 roughly hour-long workshops by 7 different speakers. With this, we took over from BristolJS who had organised a (two-day) event of this format [a year earlier](http://www.meetup.com/BristolJS/events/130960852).

What follows, is a brief description of the talks, and links to tutorials where available. For some of these it will be necessary to have [NodeJS](http://nodejs.org/) and [MongoDB](http://www.mongodb.org/) installed, if you would like to work through them. You can find a collection of linked resources at the [bottom of this post](#whippet). 

### No REST for the whippet 
The very first talk, by Tom Spencer, was in fact about using Mongoose (which lets you define schemas for Mongo collections where you need them), Node and Express to build a REST API. Tom started with a presentation about the principles of building an API. This was followed by a hands-on example in which code had to be modified in order to create a working API that manipulates entries about dogs. In the tutorial, you can check your progress by running tests, as well as peek at the right solution. Find out how to do this in Tom's [blog post](http://fiznool.com/blog/2014/09/16/no-rest-for-the-whippet). 

### Development Tools
Next up was Tessa Alexander who talked about Development Tools, focusing on the commandline. But before that she asked everybody in the audience about their background as a developer which was a great way of getting to know each other. - My favourite command is probably the "!!" (which you can use to repeat your last statement, so you can write "sudo !!" if you couldn't execute a command because of lacking permissions). Another great one is "cd -" to get back to your previous directory. You can find [Tessa's slides online](https://github.com/ta5ae/web-dev-tools-101). 

### Making maps with JS, GoogleMaps and MapBox

In the third workshop, James Barlow demonstrated how to create Maps and add dynamic elements to them. He also pointed out different mapping services like Open StreetMap and Mapbox. You can find his tutorial with demos here: [https://github.com/jmbarlow/maps-training](https://github.com/jmbarlow/maps-training)

### Refactoring 

Jack Franklin had kindly come over from London to be part of our workshop. He explained what 'code smells' make refactoring JavaScript necessary or worthwhile. He then took us through several different examples, both pure javascript and jquery. [https://github.com/jackfranklin/codehubjs](https://github.com/jackfranklin/codehubjs). Also, check out his book [The Refactoring Tales](http://javascriptplayground.com/the-refactoring-tales/refactoring-tales.html) which will be published in 2015. 

### Using the MEAN stack 

While there are some tools that let you install the compleate 'MEAN stack' (Mongo, Express, Angular and Node) &mdash; for example [mean.io](http://mean.io) or this [yeoman generator](https://github.com/DaftMonk/generator-angular-fullstack) &mdash;, Denis Sellu demonstrated how beneficial it is to understand the different parts of an application. At his company [Missionly](https://www.missionly.co.uk/), they do not use a preformatted solution. The workshop helped me understand many things that I'd not been aware of just using a scaffolding tool, and made me want to always make an effort to understand what the individual parts in a stack do.

### Introduction to Functional Programming

Nico Burns, who like Jack Franklin had already presented at the previous year's JavaScript workshop, gave a workshop on Functional programming. In JavaScript, functions can be assigned to variables, passed as arguments to other functions, and returned from functions just like numeric values. This makes it possible to for example apply functions to every item in an array, or to use a function to dynamically create a function from other functions. You can check out the examples in [theses files](http://codehub.org.uk/workshops/functional/func.zip). Nico also recommended some articles and videos, links to which you can find below in the references.

### State Machines for complex UIs 

A state machine is a way of representing a system in terms of 'states' and 'transitions'. The machine can only be in one state at a time. The transitions between states are also well-defined, and triggered by actions. Marcus Kielly showed us how you can program state machines that control for example a traffic light, or the interface of a little game. You can download the [slides and examples](https://github.com/sunwukung/smw-exercise).

This one-day workshop was very well received and a lot of the group went over to the Arnolfini afterwards and continued discussing things (sure not all Javascript though ;)) I think the material was useful to people. I can of course only speak for myself, but as time passes after this event I keep coming across things that I remember from this workshop and that give me a head start on understanding something. I am grateful to everybody who helped make it possible, my CodeHub colleagues, the sponsors and most of all the brilliant speakers. Also, to [BristolJS](http://www.meetup.com/bristoljs/), who gave great advice and helped recruit speakers. 

### References/Resources: <br />&nbsp;<br />
- <a name="whippet"></a>No REST for the whippet - Tutorial for creating test-driven REST APIs by [Tom Spencer](http://fiznool.com/)<br />
Slides: [http://slides.com/fiznool/no-rest-for-the-whippet#/](http://slides.com/fiznool/no-rest-for-the-whippet#/)<br />
Repository: [https://github.com/fiznool/no-rest-for-the-whippet](https://github.com/fiznool/no-rest-for-the-whippet)<br />
Blog post: [http://fiznool.com/blog/2014/09/16/no-rest-for-the-whippet/](http://fiznool.com/blog/2014/09/16/no-rest-for-the-whippet/)<br />&nbsp;<br />
- <a name="devtools"></a>Dev Tools by [Tessa Alexander](https://twitter.com/assetweb)<br />
Slides and examples: [https://github.com/ta5ae/web-dev-tools-101/](https://github.com/ta5ae/web-dev-tools-101/)<br />&nbsp;<br />
- <a name="maps"></a>Maps by [James Barlow](https://twitter.com/jamesbarlow)<br />
Tutorial on Github: [https://github.com/jmbarlow/maps-training](https://github.com/jmbarlow/maps-training)<br />&nbsp;<br />
- <a name="refactor"></a>Refactoring by [Jack Franklin](http://twitter.com/Jack_Franklin)<br />
Slides and examples: [https://github.com/jackfranklin/codehubjs](https://github.com/jackfranklin/codehubjs).<br />
Book: [The Refactoring Tales](http://javascriptplayground.com/the-refactoring-tales/refactoring-tales.html) <br />&nbsp;<br />
- <a name="mean"></a>The Mean Stack by [Dennis Sellu](https://twitter.com/denis_sellu) [Missionly](https://www.missionly.co.uk/)<br />&nbsp;<br />
- <a name="functional"></a>Functional Programming by [Nico Burns](https://twitter.com/nicoburns)<br />
Examples: [http://codehub.org.uk/workshops/functional/func.zip](http://codehub.org.uk/workshops/functional/func.zip)<br />
Some further material:<br />
A couple of basic introductions: [http://eloquentjavascript.net/1st_edition/chapter6.html](http://eloquentjavascript.net/1st_edition/chapter6.html) and [http://tech.pro/tutorial/1611/functional-javascript](http://tech.pro/tutorial/1611/functional-javascript)<br />
A couple of articles on currying and why it's useful: [http://blog.zakhour.me/post/javascript/simple-currying-in-javascript/](http://blog.zakhour.me/post/javascript/simple-currying-in-javascript/) and [http://fr.umio.us/favoring-curry/](http://fr.umio.us/favoring-curry/)<br />­
An article and a video on why Ramda's approach may be better than Lo-dash/Underscores (and gives you a a good overview of the landscape): [http://fr.umio.us/why-ramda/­](http://fr.umio.us/why-ramda/­) and [https://www.youtube.com/watch?v=m3svKOdZijA](https://www.youtube.com/watch?v=m3svKOdZijA)<br />
A talk on the performance optimisations behind Lo-Dash [https://www.youtube.com/watch?v=NthmeLEhDDM](https://www.youtube.com/watch?v=NthmeLEhDDM)<br />&nbsp;<br />
- <a name="statemachine"></a>State Machines by [Marcus Kielly](http://twitter.com/sunwukung)<br />
State Machine presentation and examples: [https://bitbucket.org/sunwukung/state-machine-workshop](https://bitbucket.org/sunwukung/state-machine-workshop)<br />&nbsp;<br />
