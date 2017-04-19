---
layout: post
title: "Phaser Learning Content"
date: 2017-04-18
tags: [preact, ducktable, three.cpp]
---

I discovered this great [post](https://medium.com/@bnolan/translating-sites-into-3d-with-duktape-and-preact-1723ae7264dd) by [Ben Nolan](https://github.com/bnolan?tab=repositories) today. It explains how to render in 3D each reddit thread so you could browse this on an AndroidTV, an iOs device or a VR environment.

The tech stack used for the project is really interesting:

- [three.cpp](https://github.com/jdduke/three_cpp) : a port of [three.js](https://threejs.org/) but in C++. Basically this is a simple 3D scene manager/renderer. three.cpp is C++ 11 compatible and uses OpenGL and SDL and is thus super portable.
- [Preact](https://github.com/developit/preact) : small JS library to generate a DOM. Why mix C++ and JS? More on this below.
- [duktape](http://duktape.org/): a single file C library that is an embeddable Javascript engine!

The goal of the project was to be portable and small, hence using C++. But Ben wanted users to be able to hack the way reddit threads are rendered. Hence a Javascript library (preact) with a Javascript evaluator. For now this project is not available on github but I hope it will be soon!