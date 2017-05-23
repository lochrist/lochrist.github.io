---
layout: post
title: "Language Parser"
date: 2017-05-22
tags: [parser, jison, antlr]
---

I wrote about [Context Free Design Grammar](https://lochrist.github.io/blog/2017-04-21-cfdg) a few days ago. This made me looked into implementation (both C++ and javascript) of CFDG. And this lead me to different *parser generators*. Granted writing a custom parser is [fun](https://lochrist.github.io/blog/2017-05-06-writing-a-new-programming-language) and it is easy to write one for [CFDG](https://github.com/MtnViewJohn/context-free/wiki), I still think parser technology is interesting.

### The venerable Bison

[Bison](https://www.gnu.org/software/bison/) is one of the first parser generators. It is an executable that is part of the [GNU Operating System](https://www.gnu.org). You will need to write a [Lexical analyzer](https://www.gnu.org/software/bison/manual/bison.html#Ltcalc-Lexer) and a [Grammar specification](https://www.gnu.org/software/bison/manual/bison.html#Grammar-File). Running Bison will then produce a C++ parser. You will then need to link your program with the generated Bison parser.

### Jison: Javascript Bison

[Jison](https://zaa.ch/jison/demos/) is really similar to Bison but it is all javascript based. It worked both for NodeJs and Browser. You will need to specify a Lexer and grammar file. It even uses the [Bison Gramma files format](http://dinosaur.compilertools.net/bison/bison_6.html#SEC34) (why break a winning recipe?). You will then end up with a javascript parser that can easily be used from your app. The parser will output an Abstract Syntax Tree.

### Antlr

[Antlr](http://www.antlr.org/) is yet **AN**other **T**ool for **L**anguage **R**ecognition. It has the particularity of creating a "language walker" that will call your own custom code when language features are encountered (i.e. visitor pattern). The following [mega tutorial](https://tomassetti.me/antlr-mega-tutorial/) is a wealth of information on how to use Antlr. Antlr is a java program and needs you to have a valid installation of Java 1.7 (why, oh why!). What is really great with Antlr is that it can output a parser in Python, JavaScript, Java and C#. That makes Antlr a really flexible tool. There is even a GUI that can be used to view the resulting AST.