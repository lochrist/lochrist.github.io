---
layout: post
title: "Processing with P5"
date: 2017-07-18
tags: [processing, p5, p5sketches, cfdg]
---

Some time ago I talked about [CFDG](https://lochrist.github.io/blog/2017-04-21-cfdg) which is a way to create art using a "context free grammar". This allowed a *maybe* less technical person to generate art according to simple description way easier than a full programming language. Basically this:

```
startshape start
background{b -1}
 
rule start {
    fadespiral {f 90 b 1}
}
 
rule fadespiral {
    CIRCLE {}
    fadespiral {x .9 r -4 s .997 b -.0001 hue .01}
    line {r -45 sat 1 hue 200 a -.65}
}
rule fadespiral .05 {
    fadespiral {hue .01}
    line {r 45 hue 260 sat 1 a -.65}
}
rule fadespiral .01 {
    fadespiral {f 90}
}
rule fadespiral .001 {
    start {s 4 x 25}
}
 
rule line {
    SQUARE { x .5 s .5 10 b 1}
}
```

Could turn into this:

![cfdg](https://glyphic.s3.amazonaws.com/cfa/gallery/uploads//29/98/29988429c481f219b8c5ba8c071440e1//full_960.jpg?0)

## Processing

[Processing](https://processing.org/) is the more technically advance way to create art. It was created so non-developer could use a simple, yet powerful [API](https://processing.org/reference/) to generate drawings.

Processing is a Mac/Windows/Linux **java** (sigh) app.

![processing](https://processing.org/tutorials/gettingstarted/imgs/Fig_02_01.gif)

It allows a user to use a custom scripting language to turn this:

```javascript
PVector location;  // Location of shape
PVector velocity;  // Velocity of shape
PVector gravity;   // Gravity acts at the shape's acceleration

void setup() {
  size(640,360);
  location = new PVector(100,100);
  velocity = new PVector(1.5,2.1);
  gravity = new PVector(0,0.2);

}

void draw() {
  background(0);
  
  // Add velocity to the location.
  location.add(velocity);
  // Add gravity to velocity
  velocity.add(gravity);
  
  // Bounce off edges
  if ((location.x > width) || (location.x < 0)) {
    velocity.x = velocity.x * -1;
  }
  if (location.y > height) {
    // We're reducing velocity ever so slightly 
    // when it hits the bottom of the window
    velocity.y = velocity.y * -0.95; 
    location.y = height;
  }

  // Display circle at location vector
  stroke(255);
  strokeWeight(2);
  fill(127);
  ellipse(location.x,location.y,48,48);
}
```

Into this:

![bouncing](../img/processing_bouncingball.gif)

The Processing Language has supports for classes, functions, lots of data structures, all sorts of drawing APIs, input management and even a bit of IO (read/write files).

## P5 is Processing in a browser

I am sure that in 2001, when Processing started it was all well and good to have a java app running a *custom* programming language (simpler than java). But it is 2017 and the browser is where it is at! Enters [P5](https://p5js.org/), the javascript version of Processing.

The [API](https://p5js.org/reference/) is similar (but not identical) and it is a pure javascript library so you can benefit from the browser debugger, from a known and prowerful programming language and from the welath of libraries available everywhere on github. Also, it is mighty easy to embed you p5 examples in a web page:

<iframe src='../examples/p5/p5.html' width='640' height='360'>

## Using P5 to show visual Math and Physics
