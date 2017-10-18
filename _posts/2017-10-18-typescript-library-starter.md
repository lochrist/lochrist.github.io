---
layout: post
title: "Typescript library starter"
date: 2017-10-18
tags: [typescript, library, boilerplate]
---

For Stingray, we were building and editor using web technologies in a desktop environment. Since our development tech stack was complicated enough (js, ts, lua, C#, C++, CMake, ruby) we tried to have the simplest front end setup as possible. We were not using babel. Or a bundler (webpack, rollup). We used plain javascript, requirejs and that was it.

Then we added typescript to the mix. And we tried to have the simplest environment possible as well: we only relied on the typescript compiler to transpile our code. I even wrote a [TypeScript Projects Watcher](https://lochrist.github.io/blog/2017-05-01-typescript-projects-watcher) that could watch multiple ts projects at the same time and keep compilation up to date.

## Web framework fatigue

This was all well and good since we had full control on our environement. Stingray was a closed box. Now if you are publishing any serious library on npm for others to use this is where the [javascript fatigue](https://medium.freecodecamp.com/a-study-plan-to-cure-javascript-fatigue-8ad3a54f2eb1#.g8pkgi1co) will hit you hard. There are TONS (metric) of frameworks to properly setup a build environment. Do you want [continous integration](https://travis-ci.org/)? [Tests](https://karma-runner.github.io/1.0/index.html)? [Bundling](https://github.com/rollup/rollup)? [Doc](http://typedoc.org/) generation? Automatic publishing? There are multiple frameworks for each of these tasks. Which to use? Which to pick?

### Code not setup

I hate setupping new projects with a passion. What I like is to code. To produce something new. Not read reading docs about yml config file (I am looking at you [Travis](https://travis-ci.org/)). I have a [github boilerplate](https://github.com/lochrist/vanilla-ts) to setup new typescript project. It is crazy simple. But it doesn't support much. But at least I understand all the ramifications of all the tech that is used :)

## Boilerplate to the rescue
Over the past few years, I notice a proliferation of "boilerplate" projects to start any kind of web development. There is even a tool: [Yeoman](http://yeoman.io/) whose sole goal is to help you setup any kind of webapp (over **5600** different types!).

I am currently working on my own web UI library. Because everyone has to have created one! It is kind of a rite of passage. Now that I want to put it out on npm I need to find a proper way to package it. And this is where I found this [typescript library starter](https://github.com/alexjoverm/typescript-library-starter) boilerplate. It is fully battery included: docs, tests, bundling. There is even a linter and code coverage. This seems to be a good start for my own usage... but still this is a lot of new techs to properly understand in order to maintain and debug my super simple library.

There is even a fork of this [boilerplate](https://github.com/tonysneed/typescript-library-starter-lite) in order to make some workflows (publishing and commiting) more customizable. I will try to gather enough courage to try this out shortly!