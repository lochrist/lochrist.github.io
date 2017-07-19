---
layout: post
title: "More Gui"
date: 2017-07-17
tags: [ourMachinery, imgui, redom]
---

I like UI! I said it [multiple](https://lochrist.github.io/blog/2017-03-15-imgui) [times](https://lochrist.github.io/blog/2017-03-16-small-libraries). And I recently found  three new posts on exciting new UI technology.

## Our Machinery IMGUI UI
The original creators of Stingray: Niklas and Tobias have a new venture. It is called [Our Machinery](http://ourmachinery.com/). Their development blog is incredibly interesting. And Niklas struck gold (with me at least) with its last post on [IMGUI](http://ourmachinery.com/post/one-draw-call-ui/). He explains in great great details how they implemented their UI library. The whole thing is both clean and well architectured (thanks to Niklas) and super efficient graphically speaking (thanks to Tobias). This UI example showcases what type of widgets and functionalities (docking system FTW!) they support:

![ui](http://ourmachinery.com/images/ui-sample.gif)

Obviously this is programmer art. If only we had access to the source of their library to see the internal beauty of that UI system :)

## Redom

Virtual DOM is all the craze in web UI framework (React, Preact, Mithril, Inferno...). Virtual DOM is really the IMGUI of web UI. Then on the total opposite we have the new, tiny and shiny new library called [Re:dom](https://redom.js.org/). This library **DOESN'T** use a virtual DOM. Instead 
it provides a set of helpers that makes it easier to create web view using an API might sound similar to React but that creates DOM element directly. It is thus really performant since it is basically a thin wrapper over [Vanilla JS](http://vanilla-js.com/).

This small examples shows how to create a new component and mount it on the DOM:

```javascript
import { el, mount } from 'redom';

// define Login component
class Login {
  constructor () {
    this.el = el('form#login',
      this.email = el('input.email', { type: 'email' }),
      this.pass = el('input.pass', { type: 'password' }),
      this.submit = el('button', { type: 'submit' },
        'Sign in'
      )
    );
    this.el.onsubmit = e => {
      e.preventDefault();

      const email = this.email.value;
      const pass = this.pass.value;

      console.log(email, pass);
    };
  }
}

// create login
const login = new Login();

// mount to DOM
mount(document.body, login);
```

`el` is an hyperscript syntax to create DOM element (tough you can use [JSX](https://facebook.github.io/react/docs/jsx-in-depth.html) if you prefer).

## Return to HyperApp

I [talked](https://lochrist.github.io/blog/2017-03-16-small-libraries) a little bit about [HyperApp](https://github.com/hyperapp/hyperapp) a while ago. This is a nice **super small** (about 1Kb) library that combines Virtual DOM and state management through a totally functional and stateless set of components.

### Small aparte on Elm
The whole workflow of an HyperApp webapp is based on the [Elm Architecture](https://guide.elm-lang.org/architecture/). As a side note, [Elm](https://guide.elm-lang.org/) is a totally functional language that transpiles to javascript and that can be used to create webapps. A simple "counter app"  would look like this:

```elm
-- Read more about this program in the official Elm guide:
-- https://guide.elm-lang.org/architecture/user_input/buttons.html

import Html exposing (beginnerProgram, div, button, text)
import Html.Events exposing (onClick)


main =
  beginnerProgram { model = 0, view = view, update = update }


view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (toString model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]


type Msg = Increment | Decrement


update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

```

The codepen for this app can be seen [here](http://elm-lang.org/examples/buttons).

## Getting Started with Hyperapp
[Jorge Bucaran](https://www.sitepoint.com/author/jbucaran/), the developer of HyperApp has created a great [Getting Started](https://www.sitepoint.com/hyperapp-1-kb-javascript-library/) article. If we look at the Hyperapp code of the same counter app:

```javascript
app({
  state: 0,

  // the view function make use of JSX but you can
  // use an hyperscript notation as well
  view: (state, actions) => (
    <main>
      <h1>{state}</h1>
      <button onclick={actions.add}>+</button>
      <button onclick={actions.sub}>-</button>
    </main>
  ),
  actions: {
    add: state => state + 1,
    sub: state => state - 1
  }
})
```

We see that the actions are similar to [Redux Reducers](http://redux.js.org/docs/basics/Reducers.html): pure function that computes a new state from a previous state according to a set of input. This is how HyperApp achieves its stateless components. 