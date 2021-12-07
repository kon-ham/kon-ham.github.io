---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 3
---

This is a summary of Metz’s “Practical Object-Oriented Design in Ruby". That means there is no idea here that is original to my own - I am summarizing the material for my learning and in case you might want a quick summary. All credit goes to Metz.
## "The road to maintenance nirvana is paved with classes that depend on things that change less often than they do" (Metz)

## Viewing the World Through OOP

We hold that OOP languages are efficient and effective because they reflect or model reality. Like OOP, reality is also made up of problems, objects, and the interactions between objects to provide solutions. These interactions are inescapable. Interactions happen whether or not we like them.

At first glance, seeing those interactions between those objects inside of an application can feel overwhelming. Try taking a higher level view of all those interactions. Eventually, a pattern emerges: a message is initiated by an object to invoke some kind of behavior. All of the behavior is dispersed among the objects. All behaviors are made up of an association from that object. This means that for any desired behavior, an object either knows it personally, inherits it, or knows another object that knows it.

Earlier chapters focused on single responsibility for well designed objects. Naturally then, objects must collaborate with each other in order to achieve complexity. Metz says that this collaboration between objects is both powerful and perilous. In order for one object to collaborate with another object, it must know something about that object. This knowing calls for a dependency. If you do not manage these dependencies adequately, you will strangle your application.

## Manage Your Dependencies

We might consider a dependency if when, you change one object another object must also require a change.

Take a look at your classes. The more dependencies you have, the weaker the class is, making it harder to change.

We know an object has a dependency when it knows:

- the name of another class

- the name of the message that it intends to send someone (other than `self`)

- the arguments that a message requires

- it also knows the order of these arguments. (Ordered arguments are called positional arguments)

Each of these things increase the likelihood that one class will need to change in response to another.

Dependencies in itself is not a bad thing. Objects must collaborate with each other. But unnecessary changes are bad. Unnecessary dependencies make the code less reasonable. (Metz) The addition of unnecessary dependencies results in objects that are not easy to change because small tweaks in code result in cascading changes to the rest of the code. This even affects tests. The more things are coupled together through these dependencies the more related classes move in lock step with each other, behaving as if it were a single entity.

For imagery, consider that every dependency being a dot of glue. Some dots of glue are necessary to get a job done - too many dots eventually results in a single brick of glue.

Eventually our code will get to a point where it will be easier to rewrite the entire application.

Our challenge is to create classes with as little dependencies as possible - classes that know just enough to do its job and not a single thing more. (Metz)

We may not be in a position to create these classes. We may only be in a position to reduce those dependencies.

A few examples of this would be in considering dependency injection, creating objects whose sole purpose is to create more objects which are called factories, replacement of positional arguments with keywords, or wrapping dependencies in a method utilizing objects like modules. We could also consider rearranging our dependencies.

## Things to Consider if Rearranging Dependencies

When it comes to which direction we want to swap our dependencies, consider the following:

- some classes are more likely than others to have changes in requirements

- concrete classes are more likely to change than abstract classes

- changing a glass that has many dependents will result in widespread consequences

You can actually rank all of your classes by how likely it is to undergo change relative to other classes. 

## Summary

You want to rely on classes that change less often than you do. Dependency management is core to creating future-proof applications. Control those directions if needed.

"The road to maintenance nirvana is paved with classes that depend on things that change less often than they do" (Metz)

## Was this helpful?

Outdated information? Grammar or spelling errors? Just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)