---
layout: post
title: "Lesson 3: Macros, Expressions, and Variables"
---

### Static versus dynamic

If you take an old-fashioned novel off the shelf (a "dead tree" book as some might call it) and read through it twice, it's exactly the same both times. We all know that this is just a law of nature, but in computing there's a fancy word for it: **static**. If a story's content is the same every time, it's static.

But not all paper-based books are stuck in the world of static content. There are many examples of books that allow the reader to interact with it. So-called "choose your own adventure" novels allow you to make decisions about what the main character does at key points in the story. You watch the story respond to your choice, making it a **dynamic** experience.

There's more to dynamic content than branching stories. In this unit we'll explore some of the tools that you can use in Twine to make your story more like a game, with randomness, chance, user input, and other tricks.

### Hello Macros

Twine **macros** are the core of a lot of the dynamic possibilites we mentioned above. Macros are surrounded by **double angle brackets** or ``<<`` and ``>>``. Here's a simple example of a ``print`` macro:

	<<print "hello dream world">>

When inserted into a passage, a ``print`` macro simply puts the value of the right hand side into the passage. In this case, it just puts "hello dream world" on the page. The reader never sees what the macros look like: only the creator of the story will see them. The reader of the story will see the effect they have on the page, that you control! You're probably wondering why you'd ever do this instead of just putting "hello dream world" directly into the passage. Great question! The truth is, you wouldn't, but here's why it's useful in other situations.

![Print Macro](images/variables/1.png)

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

    You've been to the Start passage <<print visted("Start")>> times. Why do you love it so much..?

Calling ``visited`` with the name of a passage inside the parenthesis is using the function with an **argument**. Many functions take arguments, some don't, and sometimes they're **optional**. As we illustrated above, you can use ``visited`` with the name of a passage as an argument, or without any arguments. The ``previous`` function can only be used with no arguments.

![Function arguments](images/variables/2.png)

### Randomness

``either()``

### Hello Variables

	<<set $x = 1>>

![Set](images/variables/2.png)

### User input

``prompt()``

### Super deep questions and fun things to try

1. Using a single passage linked to itself, create a story that counts down from 20 (or some other number) as you click on the link. When the counter reaches zero, print an amazing bit of poetry that made all of the pointless clicking worth it.

*hint: you may find the ``visited`` function and an if statement useful.*

2. Using a single passage in the same way as #1, create a story that builds a poem line by line. You can use a variable to store the text of the poem, and the ``either`` function to pick words for you. The poem might be bad... but your technique will be brilliant ;)

3. Make a story that asks for the reader's name and then gives them a compliment. Can you make the compliment different every time?

4. Make a fortune generator.

5. Make a name generator.
