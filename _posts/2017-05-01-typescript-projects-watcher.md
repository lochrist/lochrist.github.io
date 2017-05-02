---
layout: post
title: "Typescript projects watcher"
date: 2017-04-27
tags: [typescript, tspw]
---

### Converting Stingray to Typescript
We are trying, slowly but surely, to convert the whole Javascript codebase of [Stingray](https://www.autodesk.com/products/stingray/overview) to [Typescript](https://www.typescriptlang.org/). We are first renaming our JavaScript files to `.ts` assuming all of our types are `any`. And as a second pass we will add all sorts of more specialized type descriptions. We hope our story will compare to this [one](com/post/how-we-migrated-a-200k-loc-project-to-typescript-and-survived-to-tell-the-story-ciyzhikcc0001y253w00n11yb) in terms of success. Our code base is about 100k Lines of code of JavaScript so we won't be able to do this in a night. 

### How to handle multiple typescript projects?
Our current typescript setup contains multiple `tsconfig.json` (i.e Typescript project) files. We have one such project file for our core library. But each of our plugins will have its own `tsconfig.json` since plugins have a slightly different build setup than the core library. Problem is: typescript built in watcher (`tsc -w`) doesn't support watching more than one `tsconfig.json` file.

[Webstorm](https://www.jetbrains.com/webstorm/) handles this multi-project file setup really. But [VsCode](https://code.visualstudio.com/), my current editor of choice, doesn't.

### tspw
Lo and behold here comes the brand new *Typescript Project Watcher* (or tspw for short) to the rescue! I have written, with [Schmidt] (https://github.com/jschmidt42) help, a small node app that manages to start multiple `tsc` instances to watch all the `tsconfig.json` you could want to.

`tspw` is available on npm [here](https://www.npmjs.com/package/tspw) with the github repo [here](https://github.com/lochrist/tspw). Here is how to use it:

```
Syntax: tspw [options]
 
Examples:   tspw -r .
            tspw -p .\editor\core .\plugins\log_console\tsconfig.json
            tspw -r . -tsc .\node_modules\typscript\bin\tsc
            tspw -r . -tsc-args "--allowJs true --alwaysStrict true"
 
--root (-r) <rootdir> : <rootdir> and all resursive directory willl be scanned for tsconfig.json
--projects (-p) <projectDirOrFile1> <projectDirOrFile2> ... : Start watcher on the list of dir or files
--tsc (-t) <pathToTsc> : where to find tsc. By default look for globally installed.
--tsc-args <args> : string to pass to tsc
--simulate : print which watchers would be started
```

This was my first npm module published and I was surprised how easy it was. No wonder npm is filled with such a high number of (*crappy??*) modules!