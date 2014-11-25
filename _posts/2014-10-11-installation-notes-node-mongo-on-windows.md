---
layout: post
title: Notes on installing Node and Mongo on Windows
author: Carl
categories:
- javascript
- mean_stack
- node
- express
- mongo
---

What is the MEAN Stack? According to Google it is a full stack javascript  environment consisting of MongoDb, Express, AngularJS and NodeJS, but what does that really mean? Essentially that every element of the stack is written in the same language - The Data storage, the data transformation, the data manipulation - everything is all done in Javascript.

There is actually a package which does all that in one go - [Mean.io](http://mean.io) - but that's a very opinionated framework which has been very carefully considered and well supported. You may want that, or you may want to take parts of it - I'll leave that as an exercise for the user. Below is the old manual way of doing it to get everything hooked up.

As a windows user it's less well documented getting up and running on this stack so here I'll go through the tools to get you going. You will need to install the following from these locations. I prefer to use the 32 bit versions even though I'm on a 64 bit machine as I had random errors on the 64 bit.

+ Git - [http://git-scm.com/download/win](http://git-scm.com/download/win)
+ Node.js - [http://nodejs.org/download/](http://nodejs.org/download/)  (Make sure you install NPM with Node)
+ MongoDB - [https://www.mongodb.org/downloads](https://www.mongodb.org/downloads)

You need to ensure that as all tools (node, git etc) are installed that the path is encorporated. This can be done as part of the installation process - GIT and Node installs will give you the option, but if you have already got these installed you can also include the paths manually.

Eg - if git is installed at **C:\Program Files (x86)\Git\bin;C:\Program Files (x86)\Git\cmd**

Open Windows Environment Variables/Path Window

+ Right-Click on **My Computer**
+ Click **Advanced System Settings** link from the left side column
+ Click **Environment Variables** in the bottom of the window
+ Then under **System Variables** look for the **path** variable and click **edit**
+ Add the pwd to git's bin and cmd at the end of the string like this:

**;C:\Program Files (x86)\Git\bin;C:\Program Files (x86)\Git\cmd**

Do the same for Node and Mongo - make a note of the installation paths when you install these

Typically tools usually also require you to run Grunt and Bower. These can be installed by running the following from the command prompt. When you run a command prompt ensure you run is as an Administrator (in an elevated role). See here for instructions on how to do this - [http://technet.microsoft.com/en-us/library/cc947813(v=ws.10).aspx](http://technet.microsoft.com/en-us/library/cc947813(v=ws.10).aspx)

Other useful tools and links :<br />
RoboMongo - A great UI querying tool : [http://robomongo.org/download.html](http://robomongo.org/download.html)<br />
Intro in to NPM - [http://howtonode.org/introduction-to-npm](http://howtonode.org/introduction-to-npm)

NPM Folders - [https://www.npmjs.org/doc/files/npm-folders.html](https://www.npmjs.org/doc/files/npm-folders.html)<br />
Running MongoDB on Windows - [http://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/)
<p>&nbsp;</p>

### The TL:DR Key Facts ###

The following will install Grunt globally on your machine
{% highlight bash %}    
	npm install -g grunt-cli
{% endhighlight %}  

The following will install Bower on your machine
{% highlight bash %}    
	npm install -g bower
{% endhighlight %}  

Mongo : Getting started

Make a folder for the DB in your mongo folder (eg \data)
{% highlight bash %} 
mongod.exe --dbpath d:\test\mongodb\data
{% endhighlight %}  
<p>&nbsp;</p>



