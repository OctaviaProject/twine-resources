---
layout: post
title: "Lesson 4: Macros, Expressions, and Functions"
---

### Static versus dynamic

If you take an old-fashioned novel off the shelf (a "dead tree" book if you will) and read through it twice, it's exactly the same both times. We all know that this is just a law of nature, but in computing there's a fancy word for it: **static**. If a story's content is the same every time, it's static.

But not all paper-based books are stuck in the world of static content. There are many examples of books that allow the reader to interact with it. So-called "choose your own adventure" novels allow you to make decisions at key points in the story. You watch the story respond to your choices, making it a **dynamic** experience.

There's more to dynamic content than branching stories. In the next couple units we'll explore some of the tools that you can use in Twine to make your story more like a game, using randomness, chance, user input, and other tricks.

### Hello Macros

Twine **macros** are the core of a lot of the dynamic possibilites we mentioned above. Macros are surrounded by **double angle brackets** or ``<<`` and ``>>``. Here's a simple example of a ``print`` macro:

	<<print "hello dream world">>

When inserted into a passage, a ``print`` macro simply puts the value of the right hand side into the passage. In this case, it just puts "hello dream world" on the page. The reader never sees what the macros look like: only the creator of the story will see them in the body of the passage. The reader of the story will see the effect they have on the page. 

You're probably wondering why you'd ever do this instead of just putting "hello dream world" directly into the passage. Great question! The truth is, you wouldn't, but here's why it's useful in other situations.

![Print Macro](images/expressions/1.png)

Inside the angle brackets, the macro name is on the left (in this case ``print``) and an **expression** is on the right. An expression is anything in Twine that represents a value, which is usually a number or text. There are also values for "true" and "false" that we'll get into later. Since expressions can be dynamic, they aren't always represented literally in the passage. The ``print`` macro simply evaluates the expression and prints the result. For example, ``2 + 2`` is an expression that will evaluate to "4". You can use expressions to do all sorts of arithmetic. You can even "add" bits of text together. 

|Macro|Expression|Output|
|``<<print "hello">>`` | ``"hello"``| hello|
|``<<print 10 + 10>>``| ``10 + 10``|20|
|``<<print 10 - 4>>``| ``10 - 4``|6|
|``<<print "10" + "10">>``| ``"10" + "10"``|1010|
|``<<print "10" + 10>>``| ``"10" + 10``|1010|
|``<<print "hello " + "world">>`` | ``"hello " + "world"``| hello world|

This is why ``print`` is so nifty. It lets us put something on the page of our story using expressions, which give us the power to manipulate and generate text and numerical values.

### Tools for your dynamic toolbox

Let's take a look at a couple functions that get us working with dynamic content quickly. Remember the ``previous`` function that let us get the name of the previous passage? We used it in Lesson 2 to create a "back" button. We can also use it to print the name of the previous passage on the page, if we wanted. Try linking the Start passage to a passage containing the following:
 
    Hello weary traveler, I see you've just been at <<print previous()>>. How adventurous...

When you run the story, this passage should read "Start" where ``<<print previous()>>`` was located in the passage.

Another handy function is called ``visited``. This function outputs the number of times the reader has visited a certain passage.

    You've been to this passage <<print visited()>> times. 

You can also use ``visited`` to find out how many times the reader has been to a *different* passage. You do this by putting the name of the passage, in quotes, inside of the parenthesis ``()``.

    You've been to the Start passage <<print visted("Start")>> times. Have a cookie!

Calling ``visited`` with the name of a passage inside the parenthesis is using the function with an **argument**. Many functions take arguments, some don't, and sometimes they're **optional**. As we illustrated above, you can use ``visited`` with the name of a passage as an argument, or without any arguments. The ``previous`` function can only be used with no arguments.

*Insert image illustrating function arguments here*

### So Random

Here's another fun trick. You can use the ``either`` function to pick a value from a list at random. This is really helpful for creating dynamic scenery and descriptions. It can add a poetic touch to your story. To use it, insert as many words or numbers as you'd like, separating each with a comma. Be sure to put words inside quotes! Here's an example:

    The <<print either("glimmering", "glistening", "glassy", "glowing")>> light
    reflected off the wooden floor.

Here we gave four arguments to the ``either`` function. It will pick one randomly, each with a 25% chance (that's 100% divided in four equal parts). With this in our passage, a new adjective describing the light will appear each time!

You can also use numbers with the ``either`` function:

    You open a chest and find a leather pouch inside. You open it and see
    <<print either(2, 4, 6)>> glowing yellow gems inside. Whoa...

### Fun things to try

1. Using a single passage linked to itself and the ``visited`` function, create a story that counts the number of times you've clicked and prints it on the screen.

2. Using the ``either`` function, create a passage that produces a short poem that's different every time.

3. (Something to do with expressions?)
