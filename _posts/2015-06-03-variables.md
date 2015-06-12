---
layout: post
title: "Lesson 3: Macros, Expressions, and Variables"
---

### Dynamic versus Static

If you take an old-fashioned novel off the shelf (a "dead tree" book as some might call it) and read it

At least it would be super weird if it had changed. Unless you're a wizard. (Are you...?)



In this unit, we'll go over the basics of the dynamic parts of Twine. **Dynamic** parts of a story aren't always the samealways be the same. It can depend on what path you took to get to the passage, some input you gave, randomness and chance, and/or other decisions you made before arriving at the passage. We'll go over each of these mechanisms and show you how dynamic content can make your story more exciting and game-like.

### Hello Macros

Twine **Macros** are the basis of a lot of the dynamic possibilites we mentioned above. Macros are surrounded by **double angle brackets** or ``<<`` and ``>>``. Here's a simple example of a ``print`` macro:

	<<print "hello">>

When inserted into a passage, a ``print`` macro simply puts the value of the right hand side into the passage. In this case, it just pu

``visited()``

### Hello Variables

	<<set $x = 1>>

### User input

``prompt()``

### Randomness

``either()``

### Super deep questions and fun things to try

1. Using a single passage linked to itself, create a story that counts down from 20 (or some other number) as you click on the link. When the counter reaches zero, print an amazing bit of poetry that made all of the pointless clicking worth it.

*hint: you may find the ``visited`` function and an if statement useful.*

2. Using a single passage in the same way as #1, create a story that builds a poem line by line. You can use a variable to store the text of the poem, and the ``either`` function to pick words for you. The poem might be bad... but your technique will be brilliant ;)

3. Make a story that asks for the reader's name and then gives them a compliment. 