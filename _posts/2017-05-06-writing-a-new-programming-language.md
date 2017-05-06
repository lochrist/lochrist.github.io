---
layout: post
title: "Writing a new programming language"
date: 2017-05-06
tags: [dev, programmingLanguage, jai, jonBlow]
---

Strange how synchronicity works. I stumbled on this medium post 2 days ago: [I wrote a programming language Here's how you can too](https://medium.freecodecamp.com/the-programming-language-pipeline-91d3f449c919). This article explains at high level what is needed to write a programming language: Lexer, Parser, Intermediate language and possibliy transpiling. The article is interesting in that it emphasis how the author really wanted to write all the different components of its compiler toolchain by hand instead of using tools like Yak/Lex or Bison.

### Jon Blow - Reboot Conference
The same day, I watched [Jon Blow](https://twitter.com/Jonathan_Blow) great [Reboot](https://www.youtube.com/watch?v=gWv_vUgbmug) talk about *Making game programming less terrible*. Jon is creating a new language from scratch to make game programming less error-prone and more productive.

### Jai
Jon has been streaming for a while the progress on his new language. The streams are available on [youtube](https://www.youtube.com/user/jblow888). You can find a nice primer for the [*Jai language*](https://github.com/BSVino/JaiPrimer/blob/master/JaiPrimer.md) on github.

The talk highlights some really great features of Jai:

- Quick to compile: less than 0.5 seconds for a 50KLOC game! This is insanely quick. This is really *interpreter* like speed. One reason I got tired of C++ was the long compile time (especially on Maya). That kind of speed keeps you productive.
- Compile-time execution: you can use any function and Jai statement at compile time (similar to Lisp Macro I supposed). This allows you to write "compile time code" that will generate "runtime code". Or even embed a complete build system in the source of your program. As an example, Jon has created a "compile time" [Invaders](https://en.wikipedia.org/wiki/Space_Invaders) game that he can play while a program is compiling!

### Programming Languages and Debugging
I sure hope Jon continues developing this language and especially provide good tooling and debugging support for it. Programming languages live and die by the quality of their debugging tools, in my opinion. This is why I really hated coding in Lua for Stingray. Our debugging suite wasn't great especially compared to Chrome Embedded Framework Dev tools. But now that we have developed a [Debugger extension for VsCode](https://marketplace.visualstudio.com/items?itemName=jschmidt42.stingray-debug) I can safely say that Lua development for Stingray is great again!