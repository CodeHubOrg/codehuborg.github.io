---
layout: post
title: JavaScript Workshop 2015
author: Katja 
categories:
- javascript
- node
- ionic
- es6
- testing
- littlebits
---

On the 14th of November 2015, CodeHub organised another JavaScript workshop, after one that took place [a year ago](http://codehuborg.github.io/javascript/mean_stack/js_frameworks/rest_api/node/express/mongo/maps/workshop/2014/10/22/javascript-one-day-workshop.html), and [one from 2013](http://blog.kdurrani.co.uk/posts/2013-09-11-SouthvilleJS-JavaScript-workshop) which had been organised by [BristolJS](http://meetup.com/bristoljs/). This is a summary of the talks.  

### Test-driven development of Express applications using Mocha and Chai (or: How I learned to go fast)
In the first presentation, [Bridget McErlean](https://twitter.com/zubron/) talked about what TDD is, best practices, and how writing tests can make you faster; and give you a sense of achievement, too - Check out the [slides + speaker notes](https://docs.google.com/presentation/d/1ZAD4qaON2nEjTZzK10K6hF9wYkniFNVlLwdAzfLXb94/edit#slide=id.ge8b5849eb_0_59)). Then she demonstrated how to write tests on an example Express app, using [Mocha](https://mochajs.org/) and [Chai](http://chaijs.com/). The [example is up on GitHub](https://github.com/zubron/tdd-express-mocha-chai). After cloning the repository and running *npm install*, you can check out different tags. For each new test, there is one tag where the test fails, and one where it succeeds (*git tag* will show you the tags available). Also, check out the *nyan* branch, then run *npm test* ;) 
      
### Getting started with Ionic framework
[Denis Sellu](https://twitter.com/denis_sellu) walked us through the setup of an Ionic app. [Ionic](http://ionicframework.com/) is a framework built on top of [Cordova](https://cordova.apache.org/) and [Angular](https://angularjs.org/). It has a range of pre-installed elements and directives, which let you create mobile apps with relative ease. Denis demonstrated how you can scaffold a sample app with one Ionic command, then serve the app for viewing in the browser (which is different from emulating the app of course). An alternative approach for scaffolding is using a tool like [Yeoman](http://yeoman.io/). On the interface side, Ionic seems to use a lot of CSS3 techniques, like flexbox grids and CSS tranisitions for animation. Denis showed how you can create app-like interfaces with a few lines of code. To get started with Ionic, check out Denis's blog post: [http://cookieshq.co.uk/posts/getting-started-with-ionic/](http://cookieshq.co.uk/posts/getting-started-with-ionic/). There will be more posts to follow.

### Hardware hacking with Littlebits           
From mobile, we moved to hardware. [Danielle Vass](https://twitter.com/de_velopment) is an Android Developer, but also teaches children and students to code, mostly using JavaScript; in combination with SVG, or electronics. For this workshop she used the CloudBit from the [LittleBits](http://littlebits.cc/) electronic components library. The Cloudbits can connect to a web APi. As a first simple exercise we controlled the bits from the web: by pressing a button in the browser, we made the Cloudbit light up. Another example was getting wheather data through YQL(Yahoo query language) and post them to the Cloudbits. Danielle wrote a [gist with instructions](https://gist.github.com/daniellevass/bec79d14cf81142d15b6). And here are the [slides for her presentation](https://speakerdeck.com/daniellevass/littlebits-hardware-hack-at-codehub-bristol-november-2015).

<img src="img/jsworkshop_lores.jpg" style="max-width: 100%; height: auto; display: block; margin: 0 auto" alt="photo littlebits workshop" />

### Transpiling in 2015 - Not as scary as you think        
The remaining two talks concerned [ES6](http://www.ecma-international.org/ecma-262/6.0/index.html) (or ES2015). ES6 offers a whole range of new syntax and constructs that add to, and change the language considerably. [Nico Burns](https://twitter.com/nicoburns) showed how you can use ES6 today, despite lack of full browser support. The most important ingredient is a transpiler like [babel](https://babeljs.io/), which compiles ES6 into ES5. Nico showed a whole setup for development, using node, gulp and browserify, and of course babel. He went through some examples of ES5 code which he rewrote in ES6 to show the benefits. He also showed how you can use source maps to help with debugging the compiled code. Check out the setup and examples by cloning [Nico's git repository](). After running *npm install*, look at the files in the *src/* directory. When you run *gulp build*, these will be transformed into the files that you find in the *dist/* directory. 

### ES6 
While the previous talk was about how to transform ES6, the following and last one was about the features of the language. [Jack Franklin](https://twitter.com/jack_franklin) had gone "meta" and built a whole app in ES6 which allows users to work through interactive examples of ES6. In this app, we could modify some code so as to make previously failing tests pass. You started by signing in with your name. Using the [Pusher API](https://pusher.com/), Jack could receive feedback (which was displayed on a 'secret page') on who was working on which section and whether they failed or passed. Jack used [jspm](http://jspm.io/) which allows you to use any module format for your dependencies, and compiles ES6 to ES5. The web application is available here: [http://bristol-js-es6.surge.sh](http://bristol-js-es6.surge.sh) and the corresponding repo here: [https://github.com/jackfranklin/interactive-es6](https://github.com/jackfranklin/interactive-es6). 

Many thanks to all the speakers. We are also grateful to our sponsors, [Momentum](http://www.momentumfinancialtechnology.com/) and [Moltin](http://moltin.com/), who made this event possible. 

### References/Resources: 
- Repository with links to resources for workshops, slides etc.: [https://github.com/CodeHubOrg/JS-workshop-2015-resources](https://github.com/CodeHubOrg/JS-workshop-2015-resources)
- Videos: [https://www.youtube.com/playlist?list=PL_yQC45BEJ3VtbErqqaWAoJh6ibvpqBI4](https://www.youtube.com/playlist?list=PL_yQC45BEJ3VtbErqqaWAoJh6ibvpqBI4) 
- Meetup page: [http://www.meetup.com/CodeHub-Bristol/events/225911661/](http://www.meetup.com/CodeHub-Bristol/events/225911661/)
<br />&nbsp;<br /> 