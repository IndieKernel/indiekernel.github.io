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

---

**DRAFT NOTES**

- Improve association between optimization and user experience words
- Speak more about algorithms, this is also a major part of optimization

---

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

Now we understand that optimization and user experience are **tight together**, to what level of *software abstraction* can we provide the best user experience ?

## Are compilers better than us ?

---

talk about past constraints taking roller coaster tycoon as example and the fact that, now, compilers do the work better than us.

introduce algorithmic, the part that the compiler cannot do better than the human.

speak about the fact by the better algorithm we do the thinner resources usage and so provides the better user experience with execution speed, power and hardware lifetime reduce.

## Know your low layers

---

speak about knowing what operates in the low abstract layers can be benefic to work in high layers and let you optimize on the fly.

tease the next article subject with a short example of GDScript:

```gdscript

var MyClass := preload("res://MyClass.tscn")  # Load a module at runtime

func foo(bar: int) -> void:
    # Object allocation
    my_instance: MyClass = MyClass.instance()
    
    # As you add the instance to the tree, the memory handling
    # here has 2 options:
    # - deep copy
    # - move
    self.add_child(my_instance)

    # If it has moved to the add_child method, this will lead to
    # a segmentation fault. So, we have the original memory
    # print and a deep copy has been passed to add_child method.
    # Now, how Godot Engine will handle garbage collection here
    # to avoid making tons of copies and making this instance
    # kept in the scene tree ?
    # This function can possibly be called each frame O_o
    return my_instance.position
```

## So what can I do ?

---

conclusion, but optimization is always useful and can be a great challenge