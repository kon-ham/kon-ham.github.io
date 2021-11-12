---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 2
---

Please be advised: This is a summary of Metz's book "Practice Object-Oriented Design in Ruby", ch. 2. This means that credit goes to Sandi Metz and I am simply summarizing her ideas. Hope you enjoy!

## On Design

When starting out, insist that your design be simple. Model your application, using classes, to do what it needs to do now and so that change is easy to make later.

Assuming your application is successful, you will eventually need to make changes. Your ability to make easy changes will be based on your application's design. (Metz)

Easy to change is:

    - Change has no unexpected side effects
    - Small changes in requirements result in small changes in code
    - Existing code is easy to reuse
    - Easiest way to change code is to design code that is easy to change

We can understand what 'easy to change' means in the acronym 'TRUE'

T - Transparent. Consequences of changing code should be obvious to the code being changed and on other distant code that relies upon it.

R - Reasonable. The cost to change code provides a good return on investment. 

U - Usable. The code that already exists should be reusable in new and unexpected ways.

E - Exemplary. Your code should encourage others to replicate those qualities of good code.

If you can, don't try to base your design on guessing future features. In fact, don't make that decision that all. Preserve your ability to make a decision later down the road.

This applies in designing and preserving single responsibility in our classes. Because we are writing code that will eventually change, Metz says it's best to postpone making decisions until we absolutely need to.

Speaking on change, if we knew what our future requests would be, we could design the perfect application. But we do not and the world is constantly changing.

So do not feel compelled to have to make a design choice prematurely, says Metz. Instead, ask the question "what is the future cost of doing nothing today?", of which the most cost effective decision may be to wait for more information.

Therefore good designers must live in between the choice of improving now or later and making informed tradeoffs for each decision.

## Directly Referencing Complicated Structures

Direct references into complicated structures are confusing. For example, consider an array that holds a collection of more arrays. You could directly reference an array like `array[0][1]` but this is confusing and it obscures the data from what it actually is. Is the `array[0]` referring to a collection of apples? Pies? Couldn't say! 

Instead you could use something like a `Struct` method which is a shorthand way for creating a class. 

Ruby documentation explains `Struct` as: `A Struct is a convenient way to bundle a number of attributes together, using accessor methods, without having to write an explicit class.`

In this block you could create a class utilizing `Struct` that takes the collection and gives its indices names. This helps with readability and helps us to understand intent better. This also trades referencing indices of structure for sending messages to an object.

Furthermore, the cost of creating a `Struct` method is small compared to the complexities involved in changing all the code that references the indices of the structured collection.

This protects us from changes externally made to the data structure.

Utilizing a `Struct` class within another class is not ideal but this structure allows us to postpone decisions until later.

Regardless of whether or not we use `Struct`, we want to be sure that we hide away messy data or references to complicated structured collections.
## On Classes

Ultimately our object oriented application is made up of objects and the messages that pass between them, but the most visibile organizational structure of is the class.

A class should do the smallest possible useful thing: we call this having single responsibility.

Applications that are easy to change are made up of classes that are easy to reuse. 

The reusable classes with well defined behavior have few entaglements. Because of this, you can treat classes like building blocks to build your application. It's simply a matter of 'plug and play'.

The structure of your class will send a message to future developers. It reveals your design intentions and likely your code will be replicated.

## On Methods

Like classes, methods should have a single responsibility.

Like classes, methods having single responsibility allows for your code to be easily reused and easily changed.

When referring to instance variables, wrap your instance variables in methods so that you can reference a method instead of the instance variable. This allows you to be able to change the expectations of the method if change is needed rather than every occurance of the reference to the instance variable. 

If your method actually has more than one behavior, split them into separate methods. It's OK to have two separate message sends. You can refactor later. What's more important that our method has a single responsibility so that it can be easily changed later.

The other advantage to separating responsibilities in methods that have more than one behavior is that it can help you to determine if your class is highly cohesive and if that method actually belongs in its current class or if it needs to be moved to a new one.

Continue to refactor and splitting methods that have multiple behaviors into separate methods. We continue to do this because our design is not clear. These changes will feel small at first but the impact is cumulative, says Metz.

The advantages of methods having single responsibilities are as follows:

- Expose previously hidden qualities. This helps a class to be much more obvious. Methods having single responsibility has a clarifying effect on the class.

- Replace the need for comments. Consider how many comments are out of date? Out of date comments are decaying communication. If a section of your method needs commentary, separate it into another method. The new method name will serve as the commentary for the original method.

- Encourage reuse. Small methods encourage exemplary behavior. Programmers will see that method and reuse the method instead of duplicating convoluted code. 

- Easy to move to another class. Small methods are easy to move. Small methods lower barriers to improving design.

## On Single Responsibility

The path to changeable and maintainable object oriented software begins with classes that have single responsibility. 

If your class has more than one single responsibility it tends to get entangled in itself. This makes a class difficult to reuse.

Since we cannot pick and choose the behavior we want from a class when we need to reuse it, we immediately begin with problems of entanglement because our class does not have single responsibility. You could duplicate the desired aspects of the behavior from your class but this increases bugs and additional maintenance, and ultimately, the problem remains in that you have a class that is overly complicated because it is not single responsibility. 

Ultimately over reliance on such a class will cause problems later on down the road because other classes that depend on it will also likely break. 

If you cannot describe your class in a single statement then it is not single responsibility. If you must use 'and/or' to describe your class it is not single responsibility.

When everything in our class is related to its central purpose, the class is said to be highly cohesive.

Single responsibility does not necessarily dictate that our class be narrow or that we be nitpicky. We simply require that the class be cohesive, says Metz.

## Was this helpful?

Outdated information? Grammar or spelling errors? Do you just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)