---
layout: post
title: "Preact Internals"
date: 2017-03-24
tags: [preact, webDev, react]
---

I already wrote about [preact](https://github.com/developit/preact) and I impressed I am that this really small library is on par feature wise with React. Turns out, being a small library has another advantage: it makes it easier to create a code walkthrough that is easy to follow for any developer interested in the matter. [Adam Solove](https://medium.com/@asolove) has created just that: a new serie of article ([part1](https://medium.com/@asolove/preact-internals-1-the-easy-parts-3a081fa36205#.cq03hepw1), [part2](https://medium.com/@asolove/preact-internals-2-the-component-model-36a05e32957b#.6c99gdyyx)) explaining how react is implemented and how it does its magic. 

These are really in depth article that goes over the code and the algortihm behind preact vdom diffing algorithm. In part one there is also a nice blurb explaining on JSX is used to turn this:

```javascript
/** @jsx h **/
import { render, h } from 'preact';
render(<p size="5"><span>foo</span><i>bar</i></p>, document.body);
```

into this:

```javascript
/** @jsx h **/
import { render, h } from 'preact';
render(h("p",{ size: "5" }, 
    h("span", null, "foo"),
    h("i",null,"bar")
), document.body);
```

Over the last year, I have used [mithril.js](http://mithril.js.org/) as our vdom library on Stingray. I have grown used to the *hyperscript* function `m` (similar to preact's `h`) and I will admit I REALLY prefer to use `m` directly without resorting to JSX. No transpiling and the template is in Javascript (and thus fully debugaggable) are big advantages in my book.