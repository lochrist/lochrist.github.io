---
layout: post
title: "Single file C library"
date: 2017-04-17
tags: [c, singleFile, javascript]
---

It is generally easy when you work on a javascript app to integrate a third party library. Most of the time, it is just using [NPM](https://bower.io/) or [Bower](https://bower.io/) then you include the usually **single** file and you are good to go. Often, using a package manager manager is a superfluous step. Download the lib directly or link to a CDN and TADA it works. 

The burden on making a Javascript library easy to integrate is often put on the maintainer of the lib. [Nolan Lawson](https://nolanlawson.com/) wrote a great piece on this exact [subject](https://nolanlawson.com/2015/10/19/the-struggles-of-publishing-a-javascript-library/) and how a Lodash has a nice way to solve the issues for most of Javascript module system. This [snippet of code](https://github.com/lodash/lodash/blob/d65a2fbd62328868d9a6d27c860c96d51d7441c6/lodash.js#L307-L334) in the lodash depot gives a good idea of what the John-David Dalton (the maintainer of Lodash) must cope with to support everything Javascrip under the sun.

### Welcome to the C/C++ world

I used to program a lot in C++. And trust me it is much more difficult to integrate third party libraries in that "world". You always end up cursing and swearing and asking youself the millions integrator questions:

- Is the library distributed precompiled?
- If so does it work with Visual Studio 11?
- Why doesn't it support MacOS?
- Why are there 1 million header files in Qt?
- How come do I have to pay? What is LGPL? Will my code be contaminated with the GPL plague?
- Why is XCode not able to link with libXml?

### Single file library

The mirror of Javascript script "single file third party lib" is the C/C++ Single File library. The poster child for these libs are the incredibly usfuel, well maintained and easy to use: [STB](https://github.com/nothings/stb). These libraries created by [Sean Barrett](http://nothings.org/) covers a lot of 