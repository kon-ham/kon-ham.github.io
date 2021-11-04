---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 1
---
## On Ruby

Ruby is a great language to learn to program. In fact, because of it's accessibility, it can be easy to write code that lacks design or understanding of object oriented programming. Ruby will still function without this knowledge.

In Ruby, all objects come pre-equipped with behavior because all objects (we can also refer to them as things that have traits and behaviors) inherit from its class.

And since those classes are also objects that inherit from another class, we have an enormous amount of flexibility in creating data-types or behaviors.

Classes themselves can be thought of as blueprints for our objects. Within each class is a set of methods and attributes that each instantiation of a class will inherit.

Instantiation as a terminology is the act of creating a new instance of an object. As we mentioned before, creating a new instance of an object will result in that object inheriting behaviors from its class.

However, while all newly created instances of an object may hold the same types of behavior, each of those objects differ in that each object can hold its own unique data.

## Differences between an object-oriented language and a procedural programming language?

Ruby is different because there are no data-types, only objects. In fact, in Ruby, all things are objects.

Procedural programming variables can store only one data-type.

In Ruby, because what's being stored in a variable is an object, that variable can store many different types of data in a single object.

In fact, not only can Ruby store multiple data-types with each variable, but it can also store behavior. In procedural programming languages, behavior and data-types are separated and predefined.

Furthermore, new data-types cannot be created in procedural programming languages. Neither can new operations.

## On OOP

When we think of OOP, or object-oriented programming, we can think of objects and the messages they pass between each other.

OOP design is about managing the dependencies between our objects. We want to make sure that we arrange dependencies, or what each object knows about another object to a degree that change does not result in chaos because our objects.

When our objects know too much about each other, one change ends up resulting in a ripple affect where all other objects end up needing to be changed to reflect the original change. This tends to create a lot of chaos in our program and those changes tend to cost more and more each time we implement a change.

We don't want objects that are "picky". We want objects that are resilient to change. Picky objects need circumstances to be "just-right" in order to work.

This is where encapsulation comes into play. As we mentioned earlier, all objects have its own unique data while sharing behaviors from its class. Our objects encapsulate data, or hide its data from the world, and we decide how much data the object will convey to another object.

Essentially, object-oriented applications are made up of objects and the messages that pass between them.

## On Design and Cost

## Was this helpful?

I may have gotten some information incorrect or my grammar might be hard to read. Please let me know.

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)
