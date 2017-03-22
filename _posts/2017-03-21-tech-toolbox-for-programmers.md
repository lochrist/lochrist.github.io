---
layout: post
title: "Tech toolbox for Programmers"
date: 2017-03-21
tags: [dev, game, tools]
---

Each Tuesday at lunch time, our team watch a tech presentation. Recently, we watched a great GDC talk on youtube: [Tech toolbox for game programmers](https://www.youtube.com/watch?v=W_okgL6HJX8). Since I work full time on a game editor, each time I can learn about new tricks, new techs or good experiences involving tools programming I am all ears. This presentation was segmented into 5 smaller 10 min talks.

### Dialogger
The first segment was particularly interesting as it covers how to create a [dialog builder tool](https://github.com/etodd/dialogger) based on a Node Graph. [Evan Todd](http://etodd.io/) explained how he used the [jointjs](https://www.jointjs.com/) library to create his node editor. He used [NW.js](https://nwjs.io/) to make a desktop app out of its dialoger web app.

I tried dialogger and it works great and can output its result in JSON:

![dialogger](http://i.imgur.com/ojQbysn.png)

### Puzzle Script
There was a small segment on [puzzle script](http://www.puzzlescript.net/) a game engine to create puzzle game. And it comes with a built in editor. Puzzle script uses a "rule based" scripting language that is super expressive.

An example from the [documentation](http://www.puzzlescript.net/Documentation/rules101.html):

> Sokoban has one rule:
> If a player is trying to walk into a crate, try to push that crate.
> `>`is a directional arrow. The four arrows are <, >, ^, and v.

The code to moving the crate if a player is in contact with that crate would be:
```
[ > Player | Crate ] -> [ > Player | > Crate ]
```

![puzzle script](http://www.puzzlescript.net/Documentation/images/sokoban.gif)

This seems like a nice prototyping environment or even a nice challenge for a Ludum Dare or Gamejam.

### IMGUI (yet again)
The last One presenter was [Omar Cornut](http://www.miracleworld.net/) of [dear imgui](https://github.com/ocornut/imgui) fame. I already talked about IMGUI [recently](https://lochrist.github.io/blog/2017-03-15-imgui). The gist of his presentation was that if you integrate the tools INSIDE your game (using dear imgui or any other libs) you make your tools ALWAYS available to anybody having access to your game: QA, designers, developers, modders. You are closer to the game state (you are in the game after all) so it really helps understanding problems and performance.

![imgui](https://cloud.githubusercontent.com/assets/3121968/6193206/775b5d58-b37e-11e4-92bc-4dc3d39bfe21.png)