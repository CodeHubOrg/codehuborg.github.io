---
layout: post
title: Vagrant Workshop
author: Katja 
categories:
- vagrant
- provisioning
- workshop
---

Our first workshop of the year was on Vagrant and was run by [Carl Hughes](http://twitter.com/codekipple). Carl first gave a presentation about how Vagrant fit into the evolution of a developer's environment - from using Ftp for moving files to the server to using virtual machines, Vagrant and provisioning tools. These tools allow you to automatically replicate development environments and make setting up and collaborating on a project much smoother.    

In the presentation, Carl also introduced the task for this workshop, which was to get a Vagrant up and running that consisted of Ubuntu with Apache, PHP and MySQL installed. The Vagrant also had shared folders with the host OS onto which we had cloned the [CodeHub website repository](). We imported a dummy database (identical to the real CodeHub database except for user information), and could that way make a local version of the [Codehub concrete5 website](http://codehub.org.uk) run on our machines.    

The workshop was very hands-on and there were a few steps where you could get stuck, but it was good that way, because that is of course what often happens in development. It was a great way to get started. I will also use the Vagrant that I have on my machine now, when I work on the CodeHub website again, and if somebody else wanted to contribute they can use it too. - Just need to get round to it, but as I managed to update these pages now, I am hopeful!

Many thanks to Carl for the great workshop.
        
### References/Resources:           
      
- Carl's slides on Virtualisation, Vagrant, Provisioning: [http://slides.com/codekipple/vagrant101#/](http://slides.com/codekipple/vagrant101#/)   
- Virtualbox: [https://www.virtualbox.org/](https://www.virtualbox.org/)   
- Vagrant: [https://www.vagrantup.com/](https://www.vagrantup.com/)
For building a Vagrant with a local version of the CodeHub website (see slides for instruction):
- CodeHub Vagrant: [https://github.com/CodeHubOrg/codehub-vagrant](https://github.com/CodeHubOrg/codehub-vagrant)
- CodeHub website repository: [https://github.com/CodeHubOrg/CodeHub](https://github.com/CodeHubOrg/CodeHub)
- CodeHub Dummy Database: [http://tinyurl.com/lz3kefr](http://tinyurl.com/lz3kefr)
<br />&nbsp;<br />     


