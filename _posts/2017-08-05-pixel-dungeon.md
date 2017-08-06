---
layout: post
title: "Pixel Dungeon"
date: 2017-08-05
tags: [pixelDungeon, gameDev, java, roguelike, pixelArt]
---

I recently discovered an unknown [Pixel Art](https://lochrist.github.io/blog/2017-03-13-pixel-art) icon on my phone:

![pd_icon](http://is5.mzstatic.com/image/thumb/Purple49/v4/8f/25/17/8f25173a-5058-32de-4f25-a8c079b8064e/source/1200x630bb.jpg)

I clicked it and then I rediscovered the incredibly addictive and excellent [roguelike](https://lochrist.github.io/blog/2017-03-29-roguelike-development) game: [Pixel Dungeon](http://pixeldungeon.watabou.ru/). This is a game you can get for all the platforms of the world (and [Steam](http://store.steampowered.com/app/365900/Pixel_Dungeon/)) but I especially like it on a [phone](https://itunes.apple.com/app/pixel-dungeon/id1002210090). Did I mention it is free on mobile (and 3$ on Steam)? Not freemium. Not with in-app purchase. Not free with ads. It is totally free. No gimmicks. Just gameplay.

## A rogue game

Pixel Dungeon is a true Roguelike. It contains: permadeath, hunger, generated Dungeon, Amulet of Yendor and it is incredibly difficult. There is a *unrogue* feature that might be a heresy for some: it has **no** ASCII graphics but some kick ass Pixel Art sprites:

![pd](http://thenerdycool.com/wp-content/uploads/2014/05/Screenshot_2014-05-06-16-22-40-1024x576.png)

## Game design decision

Pixel Dungeon is a classic roguelike: you are a weak adventurer in a Dungeon and you are trying to get the Amulet of Yendor that sits at the 26th level below earth. Every creature wants to kill you. You will find lots of items that you know nothing about. This means all potions, scrolls, rings and weapons could be cursed and you need to either find an identifying spell or just plain try the item to see its effect. As you might expect, drinking a potion of Poison Gas is not as refreshing as you might think. It is not all: your super sword of Awesomeness (and all other items) will degrade over time! And your character will need to eat and suffer from its hunger over time. The whole game is super difficult. Expect to die very often. Even at lower levels.

![pd](http://68.media.tumblr.com/7209c33efc66a89e7a5a688f0c92f185/tumblr_nnkcie0mVu1s1kotko1_1280.png)

For more information and tips and tricks on Pixel Dungeon, checkout the [wiki](http://pixeldungeon.wikia.com/wiki/Main_Page). The [Surprise Attack](http://pixeldungeon.wikia.com/wiki/Game_mechanics/Attacking#Surprise_Attack) post is especially important as it highlights one of the core strategy of the game: using Doors to trigger Surprise Attack. 

## Brogue

I was surprised when reading about Pixel Dungeon that this game was *easy* for a roguelike.

I was also surprised, to learn that the game is not *fully* original. The author based it on another Roguelike called [Brogue](https://sites.google.com/site/broguegame/home). Brogue is a true ASCII roguelike that is still somewhat *cute* to look at:

![brogue](http://i.imgur.com/kMg9f.png)

Brogue was created to be a Roguelike with simpler stats and concepts. In fact your character only has one stat: Strenght. And this stat decides which equipment you can wear. Pixel Dungeon was created with the same design in mind.

If you want to learn more about Brogue checkout the [wiki](http://brogue.wikia.com/wiki/Brogue_Wiki). You can even play a [web version](http://brogue.roguelikelike.com/) of Brogue.

## Where is the code?

Pixel Dungeon, like a lot of Roguelike (and Brogue) is [open source](https://github.com/watabou/pixel-dungeon). The author of the game: [Watabou](https://twitter.com/watawatabou) is a one-man army who has created both the game and the art. You can look at more art by Watabou on its [Tumblr](http://watawatabou.tumblr.com/) feed.

![watabou](http://68.media.tumblr.com/23e57d9545bd93513d47d66d4278872c/tumblr_on7rrmk4tm1uk4udbo1_540.png)

You might be surprised to learn the game is coded in java... and it works on iOS! This is all possible due to [libgdx](https://github.com/watabou/pixel-dungeon-gdx) a java development framework that can be used to port Java OpenGL (ES) applications to any platform: Windows, Linux, Mac OS, Android, iOS and WebGL.

The GDX port of Pixel Dungeon can be found [here](https://github.com/watabou/pixel-dungeon-gdx).

All in all, Pixel Dungeon is truly worth dying (multiple times) for. Especially since it is free!