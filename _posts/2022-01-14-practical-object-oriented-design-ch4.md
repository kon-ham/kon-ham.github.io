---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 4
---

This is a summary of Metz’s “Practical Object-Oriented Design in Ruby". That means there is no idea here that is original to my own - I am summarizing the material for my learning and in case you might want a quick summary. All credit goes to Metz.

## Temptations of thinking in terms of solely classes

Classes are the most visible organizational structure of an object oriented application. But an applicatino is not solely made up of classes.

While OOP applications are made up of classes but they _defined_ by messages. 

Metz says that the classes control what's visible in the source code repository. But the living animated application is reflected by the messages. (Metz)

Because of this, we must also be concerned with the messages that pass between the objects. This involves thinking of what objects:
 1) Know about their own responsibilities
 2) What they know about their neighbors, which we think of as dependencies
 3) How those messages are sent back and forth to each other

## Picturing interfaces
To picture what interfaces look like, consider a woven map of fabric as messages leave visible trails behind each interaction. (Metz)

As you can imagine, as messages are exchanged between objects and as each interaction leaves behind a thread which is weaved together into one single fabric, that weave can look overly complex.

In earlier chapters of this book, Metz mentions that classes should have single responsibility. Metz also mentions that objects should have limited dependencies upon others in that an object only knows what it needs to know in order to get a job done.

But these practices, though very good, are not enough to avoid building painful design.

As illustrated with woven fabric, an overly intricate design is made up of classes that reveal too much to objects and with each method in those classes being made available to any object. 

Consider what each of your classes reveal. 

In a clear interface, messages are visibly restrained. There is some sort of an arrangement that defines which emssages are sent. These exposed methods comprise the class's public interface. (You may have seen private and public statements in your code)

## A restaurant analogy

Think of each of your classes as a kitchen. There is a single responsibility assigned for the kitchen but it utilizes many methods to get the work done. 

Customers are not allowed in the kitchen. 

The kitchen methods are private. 

The customers get what they need through a specific interface. This interface we can think of as a menu. 

The menu is public for all customers to see and to interact with. These are the public methods.

## Public vs. private interfaces
Public interfaces will:
  1) Reveal its primary responsibility
  2) Be expected to be invoked by others
  3) Will not change on a whim
  4) Be thoroughly documented in the tests

Whereas private interfaces will:
  1) Handle implementation details
  2) Are not expected to be sent by other objects
  3) Can change for any reason whatsoever
  4) Are unsafe for others to depend on
  5) May not even be referenced in tests

Public methods should read like a description of your responsiblities. These are the stable parts of your class. 

We mark private or public methods in our classes so that we can tell those that come after us to handle our code which of these methods are to be relied upon. 

Using this idea to categorize our methods, we can say that public methods are stable and private methods are inherently less stable.

This is not an easy task and Metz likens the skill to differentiate between public and private methods as an art because there is no formula, no cut and dry rules to defining between the two. (Metz)

But we want to keep in mind that we want to make a decision now that will get the job done while giving us as much space to make more informed decisions _later_.

Referring back to technical debt and costs, good public interfaces reduce cost of unanticipated change. Bad public interfaces increase the cost of change.

## Avoiding pitfalls with greenfield applications

Resist the tempation to begin coding immediately. 

You may want to immediately begin thinking of your application in terms of classes. You may begin utilizing nouns to describe classes that have both behavior and data. Those classes will be the big and visible representations of real world objects.

But be careful not to fixate on those objects. They are obvious but they are not the design center of the application. (Metz)

Good design experts notice domain objects (the large, visible, and obvious objects that reflect important real-world objects) but they do not fixate on them. Instead they focus on the messages that pass between those objects.

Focusing on the messages of those objects will help guide you to other objects that were not initially obvious to you. These are objects that you did not originally think of but are revealed through following the messages that pass between the objects.

## Sequence diagrams

Sequence diagrams through the use of "Unified Modeling Language" can help you to visualize your applications needs and to make modifications to the diagram as needed to reflect the application.

This allows you to experiment with different object arrangements and the message passing schemes. (Metz) 

These diagrams are a low-cost approach to bringing clarity and opportunities for collaboration and communication.

Again, for emphasis, these diagrams are to reflect two things: objects and the messages that pass between them. 

Sequence diagrams enable you to go from asking "I know I need this class - what should it do" to "I need to send this message, who should respond to it?"

The reality is that we don't send messages because we have objects. But rather instead we have objects because we need to send messages. 

Sequencing diagrams may help us to discover subtle differences in our understanding of our application. It may be that it is not the sender but rather the receiver of the message that needs clarification. 

Since this is a low cost approach to diagraming design, our lack of attachment to a particular approach is a feature of sequence diagramming.

Finally, Metz says that sequence diagrams "make otherwise impossibly convoluted conversations comprehensible". This goes for conversations with tech literate and illiterate alike.

## Trust and Context

Trust is the keystone of object oriented design. Objects trust other objects to get the job done without knowing the context of what an object does to get the job done.

One object says to another "I know what I want and I trust you to do your part". 

Because of this trust, it allows objects to collaborate without binding themselves to knowing all of the context of another object of how it gets a job done. 

Objects that have simple context are easy to use and easy to test. They expect very few things from the their surroundings. Objects that have complicated context are hard to use and hard to test. They require a complicated setup before they can do anything useful. (Metz)

## Changing focus from objects to messages

Focusing your attention from objects to messages allows you to build applications that are build upon public interfaces.

These interfaces, more than any of your tests or your code will define your application and determine its future. 

These 

## Was this helpful?

Outdated information? Grammar or spelling errors? Just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com)