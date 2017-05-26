---
layout: post
title: "Language Parser"
date: 2017-05-25
tags: [singleFile, header, C]
---

I keep finding more and more interesting [single file](https://lochrist.github.io/blog/2017-05-14-single-file-c-library) headers library. If only I had enough time to really try them out.

### These are tiny
I found this great collection of libraries aptly named: [tinyheaders](https://github.com/RandyGaul/tinyheaders). These have been developed by [Randy Gaul](https://github.com/RandyGaul), a game developer with a super interesting [blog](http://www.randygaul.net/). I found these libraries when a reference to a [tiny Huffman](https://github.com/RandyGaul/tinyheaders/blob/master/tinyhuff.h) algorithm popped into my twitter feed. I will admit I did not know Huffman compression actually exists. I only knew the name out of an episode of [Silicon Valley](http://news.mlh.io/i-hacked-the-middle-out-compression-from-silicon-valley-06-16-2015)! Shame on me.

### Remotery

[Remotery](https://github.com/Celtoys/Remotery) is a CPU/GPU real time debugger implemented in a single file header. Its output can be reviewed in a web app:

![ping](https://raw.githubusercontent.com/Celtoys/Remotery/master/screenshot.png)

Ironically enough the visualizing web app is about 20 files which is infinitely (or so) bigger than the profiling library itself. 