---
layout: post
title: "Coroutine"
date: 2017-04-23
tags: [coroutine, noc_turtle, javascript]
---

Recently I [wrote](https://lochrist.github.io/blog/2017-04-21-cfdg) about the [noc_turtle](https://github.com/guillaumechereau/noc) library and how it implements *Context Free Design Grammar*. Turns out noc_turtle doesn't exactly parse a "grammar" definition. It uses its own special syntax to specify a grammar.

This CFDG:

```
shape blah {
    SQUARE [s 10 y 5]
}
```

Would be coded in C as this:

```C
void blah(noctt_turtle_t *turtle) {
    START
    SQUARE(S, 10, Y, 5);
    END
}
```

`Start`, `SQUARE` and `END` are powerful macros that creates linear code for a state machine. All of this is based on [this](http://www.chiark.greenend.org.uk/~sgtatham/coroutines.html) interesting article by Simon Tatham that explains how to express coroutine in plain C.

### Coroutine in time

[Coroutine](https://en.wikipedia.org/wiki/Coroutine) have been around for a long time and allows developers to express cooperative multi-tasking. Scheme/Lisp pioneered the concept with an even more powerful mechanism called *continuation*. This [article](http://matt.might.net/articles/programming-with-continuations--exceptions-backtracking-search-threads-generators-coroutines/) showcases how *continuation* can be used to implement all sorts of dynamic flow control like: exceptions, generators and coroutine.

### Coroutine in Javascript

With ECMA6 javascript has finally access to native coroutines (and generators). This [article](https://medium.freecodecamp.com/write-modern-asynchronous-javascript-using-promises-generators-and-coroutines-5fa9fe62cf74) highlights how coroutine can help untangle the mess of asynchronous code that comes from using promises everywhere.

It also showcases 2 libaries implementing coroutines in case your programming environment doesn't support them natively.

- [co](https://www.npmjs.com/package/co): all sorts of async control flows.
- [bluebird](http://bluebirdjs.com/docs/api/promise.coroutine.html): superb libraries with support for performant promises, generators and coroutines.

### Some examples
This [article](https://x.st/javascript-coroutines/) (written in 2012!) highlights the basis of coroutine in JS. It was done obviously before most browsers would have proper support for the feature itself.

The most basic example of coroutine usage is this:

```javascript
// All the magic is express by the * near function which allow you to yield control
function* test() {
    console.log('Hello!');
    var x = yield;
    console.log('First I got: ' + x);
    var y = yield;
    console.log('Then I got: ' + y);
}

var tester = test();
tester.next(); // prints 'Hello!'
tester.next('a cat'); // prints 'First I got: a cat'
tester.next('a dog'); // prints 'Then I got: a dog'
```

This is a bit cumbersome to use. You need to keep the result of the generator function around (i.e. the `tester` variable) and to call `next` on it. I like how the article suggest a clever implementation for a `coroutine` helper:

```javascript
function coroutine(f) {
    var o = f(); // instantiate the coroutine
    o.next(); // execute until the first yield
    return function(x) {
        o.next(x);
    }
}

var test = coroutine(function*() {
    console.log('Hello!');
    var x = yield;
    console.log('First I got: ' + x);
    var y = yield;
    console.log('Then I got: ' + y);
});
// prints 'Hello!'

test('a dog'); // prints 'First I got: a dog'
test('a cat'); // prints 'Then I got: a cat'
```

Much cleaner and it kind of resembles how C# handles coroutine.