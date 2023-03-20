---
title: "Game development: Optimization"
date: 2023-03-12T17:31:37+01:00
summary: >
    We often heard about optimization in game development.
    But what is it really about ? Do we need to optimize all
    the codebase ? We'll try to respond to this
tags: [
    "game development",
    "optimization",
    "theory"
]
draft: true
---

<!-- POST COVER -->
{{< cover filename="game-development-optimization.png" caption="Take a deep dive in the low layers" >}}
<!-- /POST COVER -->

## What is optimization ?

When you try to define a concept, you're always dealing with two cases: *the academic definition* and *the personal definition*.

### The academic definition

This is what you look for in the dictionary, written by people which masters your mother tongue.
This is the **literal definition of the concept**, making a complete abstraction of the domain to which you want to apply it.

Optimization is the literal result of the optimize action itself, so let's have a look at the actual academic definition:

> **optimize** *verb*
>
> To make something as good as it can be; to use something in the best possible way
>
> **source**: *[Oxford learner's dictionary](https://www.oxfordlearnersdictionaries.com/definition/english/optimize?q=optimize)*

### The personal definition

This is your **personal perception** of the concept you have been studied before and a synthesis about **what you experimented**
by applying it by yourself.
Generally, it never goes too far from the academic one, but it is more specific, more *complex*. Not more complicated, just more complex.

Our personal definition of optimize something is the following:

> To think, design and improve something that can provides the best possible experience for anyone that will use the result produced.

As you can see, our definition is close to the academic one but with a more complex view of the concept that we're trying to define
and how about we've experimented it in the past.

A common pitfall is to confuse optimization and *refactoring* -- applying this concept to some parts of the *codebase*,
typically speaking, aims to improve the readability and the maintainability.
The desired effect in this case is to bring a value-added to the product, *a business value*.

The optimization, however, is to bring on the table the best **user experience** by doing a **thin resources control**.

## A video game is a program

From the game designer point, a video game is an interactive artistic work that provides fun to people.
His job is to design the best *gameplay* by tweaking multiple parameters such as 3Cs, challenge curve, signals, feedbacks, ...

**This is his user experience work.**

From the programmer point, a video game is an interactive software that consume **many resources** on *the system*.
His job is to apply what the game designer wants by doing a thin resources control to **make the game playable** on the target system.

**This is his user experience work**.

What interests us here, is the programmer point. There's a ton of ways to transpose a real-life problem into something executable in memory.

But there will be only one that offers the best user experience, **the most optimized resources usage**.

Now we understand that optimization and user experience are **tight together**, to what level of *software abstraction* can we provide the
best user experience ?

## Are compilers better than us ?

You may have ear that optimization is useless as compilers, in the most cases, *do a better job* than us so the effort you'll
put in optimization is a big waste.

There is only **one correct point** here: compilers are, in most cases, better than us, **now**.

Then, about 30 years ago, optimization was mandatory as computers had *a few amounts of resources available*.
This was affecting compiler's performance for a simple reason: **you couldn't have** a 200 MB loaded program to do the optimization job when your
hardware could only address 1 MB of memory.

Optimization was a **daily thing** in programmer's workflow.
However, with such hardware, **poor rigor will lead you to the worst** user experience or no experience at all.

A perfect example of an optimized game is *Roller Coaster Tycoon*.
The developer, Chris Sawyer, has entirely programmed the game in [x86 assembly](https://en.wikipedia.org/wiki/X86_assembly_language) (only 1% of [C language](https://en.wikipedia.org/wiki/C_(programming_language)) to make some [DirectX API](https://en.wikipedia.org/wiki/DirectX) calls).

> **source**: *[Chris Sawyer F.A.Q](http://www.chrissawyergames.com/faq3.htm)*

Why thus ? Because of *all the constraints* mentioned above.
Roller Coaster Tycoon can run on a large panel of hardware materials by **providing the best user experience** each time you run it.

{{< visual article="game-development-optimization" visual="rct-figure.jpg" alt_text="Roller Coaster Tycoon screenshot" caption="One of our favorite game :)" >}}

Nowadays, compilers have evolved to master instructions set while having substantial resources, in a manner that it can be OK to waste
a little of resources without too much impact on user experience.

This is a good thing for many application domains such as web development, where the value-added (refactor) and data integrity are more important than performances. Interpreted languages suits the best for this task as they provide a *high-level API* to improve productivity but compromise on performance.

Trust me, you don't want to implement a web API in C or x86\_64 assembly and **you really shouldn't do that**.

Video games are different: **the user experience is more important than the added-value**
as it rely on an interactive domain where you `(the programmer)` have to *implement the artist desire* `(the game designer)`.

But there's a point that we haven't discussed yet and which *can't be optimized by the compiler*: **algorithms**.
The algorithm choice or design is only in the human hands, as you are the one that composes the **recipe**.

This is the programmer responsibility to know if he's implementing a [O(1) or a O(N)](https://en.wikipedia.org/wiki/Big_O_notation) complexity.
The compiler or IA is **not aware** about this as it will only optimize at assembly level on *control structures*, *memory allocation* and
*data types representation*.

In a video game, the resources requested by the program can be big, very big: *fetch-decode-execute cycles*, *memory footprint*, *IRQs*, ...

The CPU and the GPU **can be very quickly manhandled**.

Optimize a game can **open interests** in reducing **power consumption** and a **fluid gameplay**, understand here a perfect user experience.
Nobody wants to play a First-Personal Shooter that crashes or provides a high ping response with a poor frame rate.

If I had to take a game as example for this, I'll go with Doom. [John Carmack](https://en.wikipedia.org/wiki/John_Carmack) is a reference programmer on this subject.

## Know your layers

---

speak about knowing what operates in the low abstract layers can be benefic to work in high layers and let you optimize on the fly.

show some basic examples as why this is important to call `queue_free`:

```gdscript
# write the example here
```

## So what can I do ?

---

conclusion, but optimization is always useful and can be a great challenge. say Chris Sawyer and John Carmack are gods. don't forget the portability point (for people that are following the reading ;) )

---

**Some reading material with this article**
+ 
