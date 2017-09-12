---
layout: post
title: "Data Oriented Physic Solver"
date: 2017-09-11
tags: [physics, singleFile, data]
---

I found this twitter post today:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">First version of my tiny data-oriented physics library is out:<a href="https://t.co/KFbpS8X91s">https://t.co/KFbpS8X91s</a> <a href="https://twitter.com/hashtag/gamedev?src=hash">#gamedev</a> <a href="https://twitter.com/hashtag/indiedev?src=hash">#indiedev</a> <a href="https://t.co/9Dj3AGZAct">pic.twitter.com/9Dj3AGZAct</a></p>&mdash; Rasmus Barringer (@rasmusbarr) <a href="https://twitter.com/rasmusbarr/status/876197661803782147">June 17, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

and I was totally blown away when I read the [blog post](http://rasmusbarr.github.io/blog/dod-physics.html) it linked to. The author, [Rasmus Barringer](https://twitter.com/rasmusbarr) exposes in great details how he created a *data oriented* [*single file*](https://lochrist.github.io/blog/2017-05-25-a-few-more-single-header) Physics solving library. This library is also *SIMD optimized*. This is a super dense amount of buzz words for a library!

The post is great because it explains how the library came to be and how the constraints of the library design (data oriented and no hidden state) would drive the evolution and iteration of the API.

The [code](https://github.com/rasmusbarr/nudge) for the library is well organized and the section with all the functions handling all sorts of SIMD operations could in itself be repackaged as a separate library that would be useful to other 3D Transformation Oriented projects.

## Box2D

Rasmus explains he uses an "impulse" approach to physics solving after having seen a GDC presentation by [Erin Catto](https://twitter.com/erin_catto) at GDC (was it this [presentation](https://archive.org/details/GDC2014Catto)?). Erin is the creator of the *IMMENSELY* populate 2D physics solving library: [Box2D](http://box2d.org/). Box2D is originally a C++ [library](https://github.com/erincatto/Box2D) but it has since been ported to [all languages](http://box2d.org/links/) known to game developers. Even [Blackberry](https://github.com/blackberry/Box2D).

This [page](http://box2d.org/downloads/) showcases a lot of other publications and presentation by Erin.