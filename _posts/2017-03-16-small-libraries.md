---
layout: post
title: "Small UI libraries"
date: 2017-03-16
tags: [dev, hyperapp, mithril, preact, goo]
---

As a developer who has worked on both big C++ applications (multi-millions lines of code) and big web app (stingray editor is about 300KLOC) I found small and well designed libraries both comforting and relaxing. It shows that software development can create concrete and well defined "unit" of work that do not need to be modified infinitely.

As an added bonus, in javascript having small code size has the intrinsic benefits of made your application faster: there is less code to download and to evaluate!

### Mithril
I discovered [Mithril](http://mithril.js.org/) after having worked with [Angular 1](https://angularjs.org/) for a few years. We had a lot of performance problem and I was looking at a library that could be mixed with Angular to optimize our Property editor.

What turned me onto Mithril at first were the SUPER great [benchmarks](https://jsperf.com/angular-vs-knockout-vs-ember/820). It was way faster than Angular or even React for that matter. But what really sold me on Mithril was its super nice and tiny [API](https://github.com/lhorie/mithril.js/blob/v0_2_x/docs/getting-started.md). In the end, we end up using only 3 functions to redo most of our performance hungry widgets! The code size of version [0.21](https://github.com/lhorie/mithril.js/blob/v0_2_x/mithril.js) was also really small (2200 LOC). It was easy enough to read it, digest it and even modify it (we added a cache system so components could be redrawn indenpendantly of each other).

Version [1.0](https://github.com/lhorie/mithril.js) is better designed and it achieves the unthinkable: it is small in code size than its earlier version!


### Goo
I interviewed a potential intern recently. A really brilliant guy who decided to work elsewhere (why , oh why?) :) I wanted to met him fro an interview as soon as I found this gem of a library on his [github](https://github.com/g-harel/goo). This  small library (501 LOC) implements a [virtual dom](https://jbi.sh/what-is-virtual-dom/) mecanism (like React and Mithril) and adds a touch of "application state management" with undo/redo and history recording.

A great piece of engineering that is both feature rich and incredibly tight in code size.

### Preact
I will admit I am not too fond of [React](https://facebook.github.io/react/). It is a great library and it has all the support that only a company like facbook can provide. Its community is big and 3rd party libraries are flourishing. But I tend to root for the underdog (Mithril for the win)!

That said, I can't help but feel that if I had to chose again, I might select [Preact](https://github.com/developit/preact). This library implements all of React API in a third of the size of React! It is even compatible with React's devTools addon. Note that it might be oversimplifcation saying that these 2 libraries are "exactly the same in terms of features". But I like the fact that Preact can pretend to be API compatible with a really smaller code size. Less is more. Or in that case, "Less is compatible".

### Hyperapp
I discovered [Hyperapp](https://github.com/hyperapp/hyperapp) by reading a post by [Gleb Bahmutov](https://glebbahmutov.com/blog//pure-programming-with-hyper-app/) (go on and subscribe to his blog). I haven't had time to use Hyperapp myself but this looks like a super promising framework: functional, using vdom and using an [Elm](https://guide.elm-lang.org/architecture/) like declarative architecture. All of this in less than 400LOC! Seriously, I read the code yesterday and I tought some files may have been missing. It turns out the whole thing was actually there in all its tiny glory!

The [documentation](https://github.com/hyperapp/hyperapp/wiki) is not the best right now. But the [examples list](https://hyperapp.glitch.me/) is very fleshed out and provide everything you need to start exploring this framework. Look for the canonical [TODOMVC](https://glitch.com/edit/#!/hyperapp-todomvc) for a nice code example.