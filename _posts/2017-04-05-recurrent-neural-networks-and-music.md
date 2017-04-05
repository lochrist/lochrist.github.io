---
layout: post
title: "Recurrent Neural Network and Music"
date: 2017-04-04
tags: [neuralNetwork, AI, learning, music]
---

I stumbled on this great (and somewhat old) [article](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) about Recurrent Neural Network recently. I will admit that I know next to nothing about Neural Network. And much less about the fact that they could be Recurrent. 

The article (written by [Andrej Karpathy](http://karpathy.github.io/)) goes into great details explaining why RNN are really good at learning. But what I found the most interesting were some of the *fun* examples the author created with a Recurrent Neural Network (RNN for short)  that would eventually learn how to write! Or how the author said it:

> we’ll give the RNN a huge chunk of text and ask it to model the probability distribution of the next character in the sequence given a sequence of previous characters. This will then allow us to generate new text one character at a time.

### Shakespeare
When fed everything that Shakespeare has written here is a sample of what comes out:

```
PANDARUS:
Alas, I think he shall be come approached and the day
When little srain would be attain'd into being never fed,
And who is but a chain and subjects of his death,
I should not sleep.

Second Senator:
They are away this miseries, produced upon my soul,
Breaking and strongly should be buried, when I perish
The earth and thoughts of many states.

DUKE VINCENTIO:
Well, your wit is in the care of side and that.

Second Lord:
They would be ruled after this chamber, and
my fair nues begun out of the fact, to be conveyed,
Whose noble souls I'll have the heart of the wars.

Clown:
Come, sir, I will make did behold your worship.

VIOLA:
I'll drink it.
```

Pretty interesting!


### Linux
When fed all the source code of the Linux kernel the RNN can write some code:

```C
/*
 * Increment the size file of the new incorrect UI_FILTER group information
 * of the size generatively.
 */
static int indicate_policy(void)
{
  int error;
  if (fd == MARN_EPT) {
    /*
     * The kernel blank will coeld it to userspace.
     */
    if (ss->segment < mem_total)
      unblock_graph_and_set_blocked();
    else
      ret = 1;
    goto bail;
  }
  segaddr = in_SB(in.addr);
  selector = seg / 16;
  setup_works = true;
  for (i = 0; i < blocks; i++) {
    seq = buf[i++];
    bpf = bd->bd.next + i * search;
    if (fd) {
      current = blocked;
    }
  }
  rw->name = "Getjbbregs";
  bprm_self_clearl(&iv->version);
  regs->new = blocks[(BPF_STATS << info->historidac)] | PFMR_CLOBATHINC_SECONDS << 12;
  return segtable;
}
```

Of course that doesn't compile. But this could fool a javascript coder :)

### Of learning

The article covers how a RNN can learn and evolve over the course of its training. Here is what its output would look like at 100 iterations:

```
tyntd-iafhatawiaoihrdemot  lytdws  e ,tfti, astai f ogoh eoase rrranbyne 'nhthnee e 
plia tklrgd t o idoe ns,smtt   h ne etie h,hregtrs nigtike,aoaenns lng
```
Not great but there is some punctuations! At 300 iterations:

```
"Tmont thithey" fomesscerliund
Keushey. Thom here
sheulke, anmerenith ol sivh I lalterthend Bleipile shuwy fil on aseterlome
coaniogennc Phe lism thond hon at. MeiDimorotion in ther thize."
```
White spaces, words and periods. Small RNN is slowly learning the language!

At iteratioin 1200:

```
"Kite vouch!" he repeated by her
door. "But I would be done and quarts, feeling, then, son is people...."
```

And finally RNN knows about spelling words and names at iteration 2000:
```
"Why do what that day," replied Natasha, and wishing to himself the fact the
princess, Princess Mary was easier, fed in had oftened him.
Pierre aking his soul came to the packs and drove up his father-in-law women.
```

### And music too
[James Blaha](https://disqus.com/by/jamesblaha/) a commenter on the article has used a similar RNN and fed it 500mb of guitar tabs in ASCII. In the end the RNN was able to compose some [music](https://soundcloud.com/optometrist-prime/recurrence-music-written-by-a-recurrent-neural-network). Not great but not bad either!

### Another use for Lua
The [code](https://gist.github.com/karpathy/d4dee566867f8291f086) for the RNN was created using a Lua framework called [Torch](http://torch.ch/). I was really surprise to see Lua used in something else than computer games (see my post on [Stingray Lua debugger](https://lochrist.github.io/blog/2017-03-25-stingray-lua-debugger)). I can only guess that the creators of Torch wanted a language that was easy to code with (especially since most scientists are not coder by trade) but that would also be MIGHTY fast. LuaJit performance on a desktop rivals that of C. And running RNN learning routines can take some crazy amount of time (hours, days and why not weeks!).
