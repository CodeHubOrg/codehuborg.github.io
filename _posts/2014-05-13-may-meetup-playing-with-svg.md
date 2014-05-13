---
layout: post
title: May Meetup - Playing with SVG
categories:
- svg
---

With increasing browser support, SVG (Scalable Vector Graphics) is finally becoming a valid option for creating images that can scale without loss across multiple viewport sizes.

There are a number of areas where SVG can be useful, for example: 

+ Icons that can be styled with css
+ Generated graphs and other diagrams like pie charts, columns charts
+ Animated images

In this workshop we will look at the anatomy of svg images and see an example of how they can be manipulated.
<p>&nbsp;</p>


### 1. Anatomy of an SVG element

In its most basic form the svg element only requires a link to the svg namespace and the version number. You can also add other namespaces. An additional namespace that makes sense to include is the xlink namespace. 

Let's start creating an svg element. 

{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >

</svg>
{% endhighlight %} 

Shapes in an svg element are being drawn on a grid that spans from the top left to bottom right. A y coordinate of 200 means that the point is drawn 200 units (in most cases pixels) from the top down.

Let's start playing with the line shape. 


{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >

<line x1="5" y1="5" stroke="red" x2="200" y2="20" />

<line x1="20" y1="40" stroke="#444" stroke-width="25" x2="120" y2="300" stroke-linecap="round" />
<line x1="20" y1="40" stroke="#cce" stroke-width="25" stroke-dasharray="5,2,14,5,7,2,8"  x2="120" y2="300"  />

<line x1="120" y1="40" stroke="#444" stroke-width="25" x2="20" y2="300" stroke-linecap="round" />
<line x1="120" y1="40" stroke="#bc8" stroke-width="25" stroke-dasharray="5,2,14,5,7,2,8"  x2="20" y2="300"  />

</svg>
{% endhighlight %} 


<iframe src="/img/lines.svg"></iframe>


### 2. More Shapes 

This is an example from the Mozilla Developer Network. Note that in an svg file you normally have an xml declaration before the svg element. 


{% highlight xml %}
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="300" height="200" >

<rect width="100%" height="100%" fill="red" />
<circle cx="150" cy="100" r="80" fill="green" />
<text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>

</svg>
{% endhighlight %} 


You can try out more shapes here: [http://scriptdraw.com/](http://scriptdraw.com/)

The most powerful shape element is \<path\>. It can be used to draw all the other elements. It has an attribute D, which contains a series of commands and parameters to draw a line. For example M 10 20 means "move to point 10 20", C stands for Cubic Bezier curve, and Q for quadratic one. Z is used for closing a shape.

For example \<path d=\"M10 10 H 90 V 90 H 10 Z\" fill=\"transparent\" stroke=\"black\"/\> 

There is a detailed section on the path element on MDN: [https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths)

<p>&nbsp;</p>

### 3. Combining and reusing shapes

We will now start creating an SVG image, which we can later animate. We will define a shape, group various elements, use them in different places in the document, and manipulate them, too. 

The \<defs\> element is used to define and element for later reuse. This could also be a gradient or pattern. 
The \<g\> element groups elements together. By assigning an id to the group element, it can be treated as a whole. 

Let's start creating a pinwheel:

First, our svg element with a title inside. It's all markup!

{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >
<title>Pinwheel</title>
</svg>
{% endhighlight %} 

We are using a /<defs/> element for the pinwheel. The id is assigned to the group inside the \<defs\> element though. Then we start drawing the stalk as a rectangle. 

{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >
<title>Pinwheel</title>
<defs>
  <g id="pinwheel">
   <rect x="300" y="250" height="320" width="16" fill="#28b" />
  </g>
</defs>
</svg>
{% endhighlight %} 

We are drawing one 'petal' of the pinwheel as two path shapes and put them in a group called "p": 


{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >
<title>Pinwheel</title>
<defs>
  <g id="pinwheel">
   <rect x="300" y="250" height="320" width="16" fill="#28b" />

      <g id="p">
        <path id="wing1" d="M 200 250 L 200 150  Q 200 50 300 50 L 300 250 Z"
         fill="#fc0"  />
        <path id="wing2" d="M 200 150 L 200 250 300 250 C 240 210 220 190 200 150 Z" fill="#ff3" />
      </g>

  </g>
</defs>
</svg>
{% endhighlight %} 

<iframe src="/img/one_petal.svg"></iframe>

To reuse the petal, we use the \<use\> element. The element that you want to reference is included as a link. Make sure that the href attribute is prefixed by the xlink namespace. The namespace also needs to be declared in the root element! 

We also need to rotate the three remaining petals at the same time. For that we use the \'transform\' attribute. Finally, we wrap the whole wheel in a group withe the id "wheel".


{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >
<title>Pinwheel</title>
<defs>
  <g id="pinwheel">
   <rect x="300" y="250" height="320" width="16" fill="#28b" />

    <g id="wheel">
      <g id="p">
        <path id="wing1" d="M 200 250 L 200 150  Q 200 50 300 50 L 300 250 Z"
         fill="#fc0"  />
        <path id="wing2" d="M 200 150 L 200 250 300 250 C 240 210 220 190 200 150 Z" fill="#ff3" />
      </g>

    <use xlink:href="#p" transform="rotate(90 300 250)" />
    <use xlink:href="#p" transform="rotate(180 300 250)" />
    <use xlink:href="#p" transform="rotate(270 300 250)" />
    </g>
  
  </g>
</defs>
</svg>
{% endhighlight %} 

<iframe src="/img/pinwheel_incompl.svg"></iframe>

Up to here, (in Firefox 29 on Ubuntu) it worked to have the svg element inline in the web page. To make the rotation visible, this is not sufficient anymore. In Chrome (34) it seems to work even less. The element needs to be embedded with an \<embed\> tag or linked to within an iframe.

<p>&nbsp;</p>

### 4. Animation

SMIL stands for Synchronized Multimedia Integration Language. Animation is achieved by adding an SVG element like \<animate\> inside the SVG element to animate. For detailed documentation check MDN: 
[https://developer.mozilla.org/en-US/docs/Web/SVG/SVG_animation_with_SMIL](https://developer.mozilla.org/en-US/docs/Web/SVG/SVG_animation_with_SMIL)

Let's complete our example and make the petals rotate (and change colour - but hey, that's done with Javascript!) as well as add a rotating dashed circle in the middle. 


{% highlight xml %}
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" >

<title>Pinwheel</title>

<script><![CDATA[
function changeColor(){
    
  var w1=document.getElementById("wing1")
  w1.setAttributeNS(null,"fill","#faa")
  var w2=document.getElementById("wing2")
  w2.setAttributeNS(null,"fill","#933")
  var A=document.getElementById("A")
  A.beginElement()
  var t=1000
    window.setTimeout("A.endElement()",t) 
  }

]]></script>

<defs>

  <g id="pinwheel">
  <rect x="300" y="250" height="320" width="16" fill="#28b" />

    <g id="wheel">

      <g id="p">
        <path id="wing1" d="M 200 250 L 200 150  Q 200 50 300 50 L 300 250 Z"
         fill="#fc0"  />
        <path id="wing2" d="M 200 150 L 200 250 300 250 C 240 210 220 190 200 150 Z" fill="#ff3" />
      </g>

    <use xlink:href="#p" transform="rotate(90 300 250)" />
    <use xlink:href="#p" transform="rotate(180 300 250)" />
    <use xlink:href="#p" transform="rotate(270 300 250)" />
    <animateTransform id="A" attributeName="transform" type="rotate" repeatCount="2" onend="changeColor()" dur="2s" from="0 300 250" to="360 300 250" />

      </g>


    <circle cx="300" cy="250" r="8" fill="#543" />
    <circle cx="300" cy="250" r="16" fill="none" stroke="#543" stroke-width="8" stroke-dasharray="3,2">
      <animate attributeName="stroke-dashoffset" repeatCount="indefinite" values="1;16" dur="1s" />
    </circle>

  </g>

</defs>

<use xlink:href="#pinwheel" transform="scale(0.3,0.3) translate(-20,-40)" />
</svg>
{% endhighlight %} 

<iframe src="/img/pinwheel.svg"></iframe>

Or an unscaled version here: [Big pinwheel](/img/pinwheel_big.svg)

<p>&nbsp;</p>

### 6. More things to do with SVG

Much of the power of SVG lies in how it can be scripted and manipulated by Javascript. Libraries like [Raphael.svg](http://raphaeljs.com/), [snap.svg](http://snapsvg.io/) and [d3.js](http://d3js.org/) are available. That would be material for another tutorial!
<p>&nbsp;</p>

### References/Resources: 
SVG Primer by the W3C:
[http://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html](http://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html)

Mozilla Developer Network:
[https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)

SVG Tutorial:
[http://tutorials.jenkov.com/svg/index.html](http://tutorials.jenkov.com/svg/index.html)


Animated Icons with snap.svg:
[http://tympanus.net/Development/AnimatedSVGIcons/](http://tympanus.net/Development/AnimatedSVGIcons/)

Icons with all the power of SVG: 
[http://useiconic.com/](http://useiconic.com/)

<p>&nbsp;</p>






