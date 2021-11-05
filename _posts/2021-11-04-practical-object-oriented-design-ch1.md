---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 1
---

**Disclaimer**
I am writing a summary of Metz's book by chapter. 

Please be advised: None of what is written below are my original ideas nor thoughts. They are all Metz's ideas. They are all great. I just want to give credit where credit is due. 

Please consider these writings a summary of her work.
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

Sandi Metz approaches design like sculpting. We must design as if we are artists in a studio that are creating custom applications for customers. It is this approach, says Metz, that is the art of arranging code.

We want to be thoughtful of design because while we could write code that perfectly reflects our current needs, we do not live in an unchanging world. Even applications that work now must face the challenge of change when people simply want more of our application.

This need for change is why design matters. Nothing is static. There is always change happening in the real world.

Poorly designed applications are a nightmare to change because programmers get deeper and deeper into the problem. And once fixed, the next iteration that calls for change will cost even more.

Undesigned programs are simple to write but impossible to change.

Sooner or later code is arranged in a manner in which _some_ design is reflected, however it is in the struggle between writing code that reflects current needs as well as arranging that code so that it has space to allow change for the future. 

Sometimes in anticipation of future needd, code is designed in a manner to reflect that anticipation. Metz says that this is overall a bad idea because practically, we never know what the future holds. Practical design does not anticipate change. Rather, it allows you room to change.

While design is important, there is a great risk in over applying design patterns in an indiscriminate way, which results in confusing and complicated code. More intemediate programmers will tend to over design principles in an attempt to apply newly learned design practices to *all of the things*.

It is up to each programmer to determine the safe zone between assessing for current needs as well as leaving space for future change. It is in this narrow space that arranging code for immediate need over practical design that our code tends to take on a technical debt, of which we will pay for in the future with each change after becoming increasingly costly.

Ignoring the reality and need for practical design will cost a programmer and an organization.

## On Agile vs. BFUD

Agile is an attempt at resolving what we do not know in terms of goals and deadline. Agile determines from the beginning that elimination of that uncertainty is impossible. 

Agile follows a practical design approach in that it immediately calls for a need for design since each iteration of Agile methodology guarantees change. Thus the code reflected must be malleable, flexible, and simple. (Metz)

Agile is a collaborative approach between programmers and customers. It believes that customers simply cannot define software if those customers cannot see the product. Agile allows us to build iteratively to gradually hit customer's needs. The interesting thing about this approach is that eventually the final product is different from what customers had imagined due to that collaborative approach.

BFUD, or big upfront design, inherently causes an adversarial relationship with customers and developers since BFUD starts with specifications, of which may not actually be related to customer needs. Because of this, when a customer actually sees the product, dislikes it, requests change, the programmers resist this since likely the change is expensive and deadlines are being missed.

Agile attempts to avoid this confrontational approach by building small, iteratively, and collaboratively with customers.
## On Measuring Good Design

Good design can be (sort of) measured. The best metric to great design, according to Metz is the _cost per feature over the time interval that matters_. That is, measure the cost of each change that takes place in the future in the relevant areas.

## Was this helpful?

I may have gotten some information incorrect or my grammar might be hard to read. Please let me know.

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)
