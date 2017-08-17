---
layout: post
title: "Virtual DOM"
date: 2017-08-19
tags: [virtualDom, react, inferno]
---

Virtual Dom is to Web UI what [IMGUI](https://lochrist.github.io/blog/2017-03-15-imgui) is to C++ UI: a way to draw UI without keeping references to a complicated widgets hierarchy. This paradigms really helps decouple the UI from the model. And it especially makes it easy to update ANY part of the model and to refresh the ui in an efficient way without having complicated code to actually update the ui values.

## How does that work

Basically you create a structure describing the DOM you would have built. Then you compare the previous "cache" result of the same UI and only apply the difference to the actual DOM. This workflow is built on the assumptions that updating the DOM is slow (it is) while creating a structure of Plain javascript objects and comparing that structure is quick (it is *usually*).

This [article](https://medium.com/@rajaraodv/the-inner-workings-of-virtual-dom-666ee7ad47cf) explains all you need to know about virtual DOM in much greater details. I espcially like the block diagram explaining the whole virtual DOM lifecycle:

![vdom lifecycle](https://cdn-images-1.medium.com/max/2000/1*TF0TZszVwpYc1Pba7Dbk7Q.png)

The article itself contains a lot of code snippets. Lots of them coming directly from [Preact](https://github.com/developit/preact), the smaller (and faster) version of ReactJS. I talked about Preact in another [post](https://lochrist.github.io/blog/2017-03-16-small-libraries) and I highlighted what I like about that framework: its small code size makes it easy to read and understand. And you can, in no time time, get a good comprehension of how the *inner gears* are turning. Preact code base is easy to read and becomes a tutorial on how virtual DOM and diffing actually work.

### snabbdom

This [article](https://medium.com/@yelouafi/react-less-virtual-dom-with-snabbdom-functions-everywhere-53b672cb2fe3) explains how to create a virtual DOM application using [snabbdom](https://github.com/snabbdom/snabbdom) another vdom library. 

What is interesting in that article is how you can use functional programming to create a truly reactive application:

![reactive](https://cdn-images-1.medium.com/max/800/1*A8VYQeV7MOWEzJslNjZehg.png)

The whole architecture of the application is based on [Elm](http://elm-lang.org/), a purely functional language that transpiles to javascript and that comes with a good ui library.

![elm](https://cdn-images-1.medium.com/max/800/1*V4VKLsiO7cfCuf0nlgBoxA.png)

### Is vdom really fast?

There are litterally hundreds of web UI frameworks. Dozens of them are using vdom. Is it true that vdom is fast? If you go to any vdom library site, you will see lots of benchmarks telling they are *blazingly* fast (always blazing). But can you trust those benchmarks? 

I recently found this INCREDIBLE [website](http://www.stefankrause.net/js-frameworks-benchmark6/webdriver-ts-results/table.html#) that has lots of benchmarks involving almost any web frameworks. These benchmarks are updated as soon as a new version of ANY framework is updated.

I selected a few of the most well know framework and here are the results:

![bench](../img/vdom-benchmarks.png)

What can we learn from this? That most vdom (mithril, preact, react, vue) are fast. That old school framework like Marionnette are SUPER slow. And we learn that [Inferno](https://infernojs.org/) is *almost* as fast as using Vanilla JS!

Inferno is a web framework that doesn't get much press but it is *lightning fast*. It is a bit bigger than preact and mithril but its performance are off the roof. I really need to try it soon!