---
layout: post
title: "Roguelikes"
date: 2017-03-13
tags: [roguelike, rpg, dev]
---

I always liked old school RPG like Dungeons and Dragons. I like *Dungeon Delving*. Both in computer games and in boardgames. The epitome of getting deep down a dungeon in search of loot, fame and death is the whole [Roguelike](https://en.wikipedia.org/wiki/Roguelike) genre of games.

### Books

I recently read a good [book](https://www.amazon.ca/Dungeon-Hacks-NetHack-Angband-Roguelikes-ebook/dp/B012QP0Z7O/ref=sr_1_4?ie=UTF8&qid=1490925377&sr=8-4&keywords=roguelike) that covered the whole history of Roguelikes and how these games who are often sparse (to say the least), difficult (brutally so) and opaque (nethack!) have had a super influence on the gaming industry.

Could you believe that without this:

![rogue](https://upload.wikimedia.org/wikipedia/commons/0/00/Nethack_releasing_a_djinni.png)

There wouldn't be this:

![diablo](http://alldiablo3.com/wp-content/uploads/2012/01/Diablo_III_ss03.jpg)

### Desktop Dungeon

One game semi-roguelike game that really caught my eyes these last years is [Desktop Dungeon](http://www.desktopdungeons.net/). I first stumble on the free version:

![dd](http://www.desktopdungeons.net/wp-content/uploads/2011/03/screens_0_15b.png)

I was amaze how this was a total mix of boardgames mecanisms and Roguelike. It was incredible how the management of your resources: health, items and **monsters** necessitate to be tight or you would die horribly. The small lenght of a dungeon exploration and the fact that you would get to unlock new characters and items made the game really addictive.

The new version (available on **ALL** possible platforms) is really better looking:

![new dd](http://www.desktopdungeons.net/wp-content/uploads/2011/03/upsell_031.png)

But the gameplay is as tight. The whole "overworld management" of your village and heroes has improved a lot since the free version. This feels like a "big" game.

### Darkest Dungeon

Another game that made me sink enormous amount of time recently is [Darkest Dungeon](http://www.darkestdungeon.com/). I played it in early access. Then rediscovered it when it was officially launched. This is another semi roguelike games. But this time you are managing a party of heroes. Lots of character classes. Lots of Skills. Lots of combos. But that is really the tip of the iceberg. This game is really the total package. Sound direction is incredible (this narrator is so great). The Art direction is exceptional. Those 2d really dark graphics are really unique. And the stress system blew my mind. You characters will become psychotic, masochist, fear light, and love to hurt their own party!

![darkest](https://cdns.kinguin.net/media//category/2/-/2-1024_2862.jpg)


### Development

It has always been one of my dream developing my own brand of roguelike. And there are a lot of resources to help me do so.

Gamasutra/Reddit host a definitive [list of all sorts of discussions](http://www.gamasutra.com/blogs/JoshGe/20170207/290928/Two_Years_of_Roguelike_Development_FAQs.php?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+GamasutraFeatureArticles+%28Gamasutra+Feature+Articles%29) about roguelike development. It is a wealth of information that covers both design of systems and implementation suggestions.

[Rot.js](http://ondras.github.io/rot.js/hp/) is a nice *javascript* library that provides all sort of features needed in a roguelike:
- Map generation
- Lighting
- Pathfinding
- Combat system

You can also look at the sources of a javascript implementation of [Desktop Dungeon HTML5](http://www.desktopdungeons.net/HTML5/) to get a good example of how this game is made.

And you can always go back to the sources (pun intended): most old school roguelikes are already [open source](https://en.wikipedia.org/wiki/Category:Open-source_roguelikes). Sometimes in order to learn all the intricacies of nethack, there is nothing like the git depot of the whole [game](https://github.com/Vanilla-NetHack/NetHack)!



