---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 5
---

This is a summary of Metz’s “Practical Object-Oriented Design in Ruby". That means there is no idea here that is original to my own - I am summarizing the material for my learning and in case you might want a quick summary. All credit goes to Metz.

####
"Messages are the center of object-oriented applications, and they pass among objects along public interfaces" (Metz)

## On Object Oriented Design
The purpose of object oriented design is to reduce cost of change. The messages are at the design center of your application. When we combine rigorously designed public interfaces while being aware that the messages are the center of our application, we can create what is called duck typing.

Flexible applications are built on objects that operate on trust; it is your job to make your objects trustworthy. This means that your object does not need to know about how another object gets the job done - only that it will do the job when asked.

The purpose of design is to lower costs; this is the measuring stick you should always carry with you.

## On Polymorphism
In Greek wording, polymorphism means to say that a message has many forms.

In OOP, polymorphism refers to the ability of many different objects to respond to the same message: senders of the message don't care about the class of the receiver, the receivers supply their own specific version of the behavior.

Polymorphism assumes that the message is interchangeable from the sender's point of view. An object implementing the message of the sender can be interchangeable with another. The sender doesn't need to know or care about this substitution. (Our application demonstrates trust throughout the interactions of objects)

When implementing polymorphism, it is up to you to make sure your objects are well behaved.

There are many ways to achieve polymorphism. One way is duck typing.

## On Duck Typing
"Duck typing takes the public interfaces from those classes and creates virtual types that are defined by actions rather than what they are" (Metz)

Duck types are public interfaces that are not tied to any specific class. Because of that, they are chameleons that are more defined by their behavior than by their class.

We don't need to assume that a Ruby object can only respond to one interface. In fact, we can have our Ruby objects respond to many different public interfaces.

In fact, a Ruby object's class is only one way for an object to acquire a public interface. We can create public interfaces in our applications that cut across class. 

It's not what an object is that matters. It's what an object does.

If our objects can inherently trust others to do the necessary job without knowing how it does that job and if we can assume that an object can be any kind of object, we have what Metz says are near infinite possibilities.

Duck typing exists as an abstract. It lies within concrete and abstract code, where concrete code is easy to understand but costly to extend and where abstract code can be initially more obscure but once understood is far easier to change.

Using duck typing will take your concrete code and move it more abstract. 

Duck typing reveals abstractions that might be otherwise invisible.

The ability to tolerate ambiguity about the class of an object is the hallmark of a confident designer. Once you treat objects as if they are defined by their behavior rather than by their class, you enter into a new realm of expressive flexible design.

It is relatively easy to implement a duck type. But the challenge is in noticing you need one and to abstract its interface

Many times unacknowledged ducks exist - you can replace the following with ducks:
	- case statements that switch on a class
	- `kind_of?` and `is_a?`
	- `responds_to?`

When you see these repeating patterns of badness in your code, concentrate on the offending object's expectations and use those expectations to find a duck type. Once you have a duck type in mind, define its interface, and implement that interface where necessary, and then trust those implementers to behave correctly.

When your code seems to imply 'I know who you are therefore I know what you do' you might want to consider duck typing because this code implies a lack of trust in collaborating objects. This weighs your code down. It introduces dependencies that make code difficult to change.

Ultimately, the decision to create a new duck type relies on judgement.

## Designing Sequence Diagrams
Be wary of overly complex sequence diagrams. The whole point of a sequence diagram is that it is simple. In fact, according to Metz, sequence diagrams should always be simpler than the code they represent.

## Was this helpful?

Outdated information? Grammar or spelling errors? Just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com)