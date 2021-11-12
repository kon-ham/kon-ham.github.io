---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 1
---

Please be advised: This is a summary of Metz's book "Practice Object-Oriented Design in Ruby", ch. 1. This means that credit goes to Sandi Metz and I am simply summarizing her ideas. Hope you enjoy!

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

## On Classes

Ultimately our object oriented application is made up of objects and the messages that pass between them, but the most visibile organizational structure of is the class.

A class should do the smallest possible useful thing: we call this having single responsibility.

Applications that are easy to change are made up of classes that are easy to reuse. 

The reusable classes with well defined behavior have few entaglements. Because of this, you can treat classes like building blocks to build your application. It's simply a matter of 'plug and play'.

The structure of your class will send a message to future developers. It reveals your design intentions and likely your code will be replicated.

## On Methods

## On Single Responsibility

If your class has more than one single responsibility it tends to get entangled in itself. This makes a class difficult to reuse.

Since we cannot pick and choose the behavior we want from a class when we need to reuse it, we immediately begin with problems of entanglement because our class does not have single responsibility. You could duplicate the desired aspects of the behavior from your class but this increases bugs and additional maintenance, and ultimately, the problem remains in that you have a class that is overly complicated because it is not single responsibility. 

Ultimately over reliance on such a class will cause problems later on down the road because other classes that depend on it will also likely break. 

## Was this helpful?

Outdated information? Grammar or spelling errors? Do you just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)