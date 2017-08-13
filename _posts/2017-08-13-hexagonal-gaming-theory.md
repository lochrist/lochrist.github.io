---
layout: post
title: "Hexagonal Gaming Theory"
date: 2017-08-13
tags: [gaming, phaser, hex]
---

I like [boardgames](https://lochrist.github.io/blog/2017-03-18-boargames). And I like boardgames with hexagons. My favorite boardgame is [Mage Knight](https://www.boardgamegeek.com/boardgame/96848/mage-knight-board-game) and it makes great use of a dynamic map that you build over time from tiles containing multiple hexagons:

![hex](https://cf.geekdo-images.com/images/pic1091942_md.jpg)

At some point in my programmer life I did an adaptation of the solitaire Civilization game: [Pocket Civ](https://www.boardgamegeek.com/boardgame/28044/pocket-civ). This game uses hexagons to represents the differents regions containing resources and tribes. For that particular project I was using [Google GWT library](http://www.gwtproject.org).

![pocket civ](https://cf.geekdo-images.com/images/pic300025_md.jpg)

These days I am fiddling around with [PhaserJS](http://phaser.io/) a great 2D Javascript game engine with a wealth of [documentation](http://phaser.io/docs/2.6.2/index) and [tutorials](http://phaser.io/learn/official-tutorials). I found this incredibly thorough tutorial by [Juwal Bose](https://tutsplus.com/authors/juwal-bose?_ga=2.196878255.2031824736.1500038629-2124315838.1500038629) on how to create a [hexagonal minesweeper game with Phaser](https://gamedevelopment.tutsplus.com/tutorials/creating-hexagonal-minesweeper--cms-28655). The tutorial goes into great lengths on how to implement layouting, selection and all sorts of hexagons manipulation. Well worth a read!

![hexes](https://cms-assets.tutsplus.com/uploads/users/1605/posts/28655/final_image/hexmine-phaser-finished.png)