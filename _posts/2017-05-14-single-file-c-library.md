---
layout: post
title: "Single file C library"
date: 2017-05-14
tags: [c, singleFile, javascript]
---

It is generally easy when you work on a javascript app to integrate a third party library. Most of the time, it is just using [NPM](https://bower.io/) or [Bower](https://bower.io/) then you include the usually **single** `js` file and you are good to go. Often, using a package manager is a superfluous step. Download the lib directly or link to a CDN and *TADA*: it works. 

The burden of making a Javascript library easy to integrate is often put on the maintainer of the library itself. [Nolan Lawson](https://nolanlawson.com/) wrote a great piece on this exact [subject](https://nolanlawson.com/2015/10/19/the-struggles-of-publishing-a-javascript-library/) and how Lodash has a nice way to solve this issue. This [snippet of code](https://github.com/lodash/lodash/blob/d65a2fbd62328868d9a6d27c860c96d51d7441c6/lodash.js#L307-L334) in the lodash depot gives a good idea of what John-David Dalton (the maintainer of Lodash) must cope with to support every Javascript module systems under the sun.

### Welcome to the C/C++ world

I used to program a lot in C++. And trust me it is much more difficult to integrate third party libraries in that "world". You always end up cursing and swearing and asking yourself million questions:

- Is the library precompiled?
- If so does it work with Visual Studio 11?
- Why doesn't it support MacOS?
- Why are there 1 million header files in Qt?
- How come do I have to pay? What is LGPL? Will my code be contaminated with the GPL plague?
- Why is XCode not able to link with libXml?

### Single file library - STB

The mirror of Javascript "single file third party library" is the C/C++ Single File library. The poster child for these libraries are the incredibly useful, well maintained and easy to use: [STB](https://github.com/nothings/stb). These libraries created by [Sean Barrett](http://nothings.org/) cover a lot of different subjects from image manipulation, to fonts rendering and to all sorts of data structure utility.

Sean has a great [single library howto](https://github.com/nothings/stb/blob/master/docs/stb_howto.txt) document explaining how he packages his libraries.

### Other Single File Libraries

It seems STB has helped to create a *Single file library movement*. Sean has a big [list](https://github.com/nothings/single_file_libs) of such libraries on his site.

Some interesting libraries, in my opinion, are:

### Miniz

This [library](https://github.com/richgel999/miniz) is a z-lib replacement in a single file. Incredibly easy to use, this is what we chose for our Zip support in Stingray Editor.

### Nuklear

I have already written about my love of UI and especially [*Immediate GUI*](https://lochrist.github.io/blog/2017-03-15-imgui). [Nuklear](https://github.com/vurtun/nuklear) is a single file IMGUI C library! It even uses stb for fonts and text rendering. 

![stb](https://cloud.githubusercontent.com/assets/8057201/11761525/ae06f0ca-a0c6-11e5-819d-5610b25f6ef4.gif)

![stb2](https://cloud.githubusercontent.com/assets/8057201/14902576/339926a8-0d9c-11e6-9fee-a8b73af04473.png)

### Debuginator

A single file [game debugger menu](https://github.com/Srekel/the-debuginator). This library was used by Fat Shark to ship their latest game: *Warhammer End Times - Vermintide* (which is a game that uses Stingray as its game engine).

### noc turtle

This last [library](https://github.com/guillaumechereau/noc) is used to render images using a [CFDG](https://lochrist.github.io/blog/2017-04-21-cfdg) like grammar. It is interesting both for its tricky usage of macros to generate [*coroutine*](https://lochrist.github.io/blog/2017-04-23-coroutine) like code and also because it was used to produce art for the [Blowfish Rescue](https://noctua-software.com/blowfish-rescue) game.

![noc](https://noctua-software.com/static/blowfish-rescue/screenshot-5.png)