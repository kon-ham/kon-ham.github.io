---
layout: post
title: Summary of "Practical Object-Oriented Design in Ruby", Ch. 6
---
This is a summary of Metz’s “Practical Object-Oriented Design in Ruby". That means there is no idea here that is original to my own - I am summarizing the material for my learning and in case you might want a quick summary. All credit goes to Metz.

## Well designed applications are constructed of reusable code (Metz)

The objects of those well designed applications are small, trustworthy with minimal context, clear interfaces, and injected dependencies that are inherently reusable.

Be mindful when you create objects that say to another object - 'I know who you are, and because of that, I know what you do'  (Metz) This sort of knowing of another object results in increasing dependencies of that object.

If an object needs to check itself or an attribute of itself - consider the previous chapter's usage on duck typing. That is, many times unacknowledged ducks exist - you can replace the following with ducks:
- case statements that switch on a class
- `kind_of?` and `is_a?`
- `responds_to?`

## On Inheritance
Inheritance solves the problem of dealing with related types that "share a great deal of common behavior but differ across some dimensions." (Metz)

"Inheritance allows you to isolate shared code and implement common algorithms in an abstract class, while also providing a structure that permits subclasses to contribute to specializations." (Metz)

Ultimately, inheritance is, at its core, a mechanism for automatic message delegation. It defines a forwarding path for not-understood messages. It creates relationships in a manner that if it cannot respond to a received message, it delegates that message to another.

This behavior is inherent. You simply define the inheritance relationship between two objects and the message forwarding happens automatically.

Typically, or classically, as Metz says, this happens by defining subclasses. These messages are forwarded from subclass to superclass. This shared code is defined in the hierarchy. (Metz)

Recall the facts about an object. An object receives messages. Regardless of the complexity of the code, the receiving object takes the message and handles it in two ways: it either responds directly or it passes the message on to another object for a response. (Metz)

Inheritance allows for us to automatically pass a message onto another object if the first object does not understand the message.
Some programming languages allow for multiple inheritance. Ruby does not have this feature and instead only allows for one single inheritance through a superclass. A superclass may have many subclasses but a subclass can only have one superclass.

When you have instantiated any new object, you have participated in inheritance. A string, integer, or float makes its way up the inheritance hierarchy and eventually reaches `Object`. This upward trajectory of object message delegation implies a subclass is everything a superclass is but more. (Metz)

Metz lays out two rules in order for inheritance to work:
- The inheritance pattern must follow a generalization -> specialization relationship when it comes to superclass to subclass.
- You must use the correct coding techniques

When built correctly, the inheritance relationship is the easiest way to extend outwards with new subclasses. This is inheritance's greatest strength, according to Metz.

Metz concludes that if needing numerous specializations from a stable and common abstraction, inheritance can be an extremely low cost solution. (Metz)

## An example
With a few examples, Sandi Metz demonstrated the problem in which a `Bike` class was attempting to different many different instantiations of a `Bike` object. Consider the many different styles of a bike: mountain bike, beach bike, road bike...

Metz continues, 'Some of `Bicycle`'s behavior applies to all bicycles, some only to road bikes, and some only to mountain bikes. This single class contains several different, but related, types. This is the exact problem that inheritance solves: that of highly related types that share common behavior but differ along some dimension.' (Metz)

Though we can use inheritance in our objects, that does not mean we want to blindly apply the inheritance of a superclass into a subclass; for example a `Mountain Bike < Bike` inheritance relationship can be useful simply for applying inheritance to our objects - but consider if `Mountain Bike` is now inheriting behavior from `Bike` that does it make any sense nor is applicable to `Mountain Bike`. We do not want to needlessly inherit behavior that we do not want or do not need.

Metz demonstrates how design can evolve. Earlier in our examples we find that the design for `Bike` class was fine assuming all `Bike`s were roadbikes. But now that mountain bikes exist as a subclass of a `Bike`, the code must reflect that specification of inheritance.

Metz says subclasses are specializations of superclasses. In our case, `MountainBike` should be everything `Bike` is, plus more (Metz)

This means that an object that's expecting a `Bicycle` should be able to interact with `MountainBike` in ignorance of its actual class. (Metz)

In our new iteration of `Bicycle` as a superclass, we no longer need to apply `.new` to `Bicycle` because it is now an abstract class.
 
This means we can expect to create `MountainBike` or `RoadBike` but never `Bicycle` because `Bicycle` no longer represents a whole bike.

## Abstract classes
The whole existence of an abstract superclass is to be subclassed. 

Metz says they provide a common repository for behavior that is shared across the subset of subclasses - subclasses that in turn supply specializations.

## Abstracting out superclasses by pushing code down and then up
Note - it's probably best to start abstracting a superclass when you have more concrete examples of subclasses - in Metz's case she believes at least 3 should exist, otherwise you should wait before making this decision.

In general, if you only expect to have one subclass from a superclass, you'll want to question why you're doing that. In general, unless you have a reason to implement inheritance - `Bicycle` will good enough. (Even if you are anticipating including more subclasses later - as Metz says, that day may never come)

Even within this context of having two subclasses of `Bicycle`, that may not be enough to justify the existence of an inheritance relationship. While having two subclasses of bicycles helps us to know how to deal with the details of abstraction, we would benefit from having more subclasses. Metz says that creating this hierarchy of inheritance has costs - we want to be sure that we get the abstraction right before our subclasses depend on them - therefore it may be best to put off creating this relationship until the time is right.

A method for abstracting out inheritance between super and subclasses. Metz actually recommends taking the code that now exists within the superclass to move it completely down the hierarchy into a subclass. There a few reasons for this:

- It's a simple problem to solve when you are sending code back up to the superclass which now acts as an abstract class - given that there is a cost to implementing change the cost for the change of abstraction is finding out that it does not work as opposed to leaving behind dependencies.
- Junior to experienced coders are able to abstract out the hierarchy because they go from 'it does not work' to 'it works' workflow as you slowly and carefully pick out what methods need to go back to the superclass.
- Since the problem exists in the perspective of 'this subclass is not working adequately because it is not sending up the inheritance chain the appropriate message' instead of 'this works but we have to abstract this material out' the scope of the problem is smaller and much easier to notice because it simply does not work. If you work the opposite direction you are at risk of leaving remnants of concrete code. (Metz)

Best way to create an abstract superclass is to take the code in the superclass, push it down into its subclasses, and individually pick which code to push back up.

## Template method patterns and hook methods
Template method pattern is defining a basic structure in the superclass and sending messages to acquire subclass-specific contributions (Metz)

In the case of our `Bicycle` superclass, a method in the superclass of 
```
def default_chain
    "11-speed"
end
```
is given so that all subclasses inherit a default-chain of "11-speed" but each subclass specifies its default tire size, which is different for `RoadBike` and `MountainBike`. A specific downside for this design is that so far we mandate that subclasses of `Bicycle` require specifying a bicycle size upon each instantiation of the object (ex. `bent = RecumbentBike.new(size:  "L")`)

Consider this example:
```
class RecumbentBike < Bicycle
    attr_reader :flag

def intialize(**opts)
    @flag = opts[:flag]    # forgot to send `super`
end


bent = RecumbentBike.new(flag: 'tall and orange')
puts bent.spares

# => {:tire_size=>nil,      <- didn't get initialized
# =>  :chain=>nil,
# =>  : flag=>"tall and orange"}
```

What's happening here is that on top of demanding that subclasses know what they do, we also demand that subclasses know how they are supposed to interact with their superclass, increasing dependency between the two, creating more tightly coupled classes - this is not what we want. Not only that, we're now duplicating code because all subclasses of `Bicycle` are now required to send super in all the same spaces.

When a subclass sends `super`, it is declaring that it knows the algorithm of the inheritance relationship. Metz in fact says that now this subclass *depends* on this knowledge.

The moment this algorithm changes, those subclasses may also break because of those dependencies.

**NOTE**
Using `(**opts)` indicates that you can include any number of arguments within the initialize method. They are returned as a hash. ie.
```
def initialize(**opts)
@size = opts[:size]
@tape_color = opts[:tape_color]
end
```

While we can make use of method templating, this requires the use of sending `super` in each subclass of that superclass. Doing so repeats code and therefore increases the dependencies of that code, increasing the cost of change. Furthermore, while we can expect a programmer to understand the expectations of a superclass, it is very easy to forget to send `super` from a subclass.

These abstract superclasses can use method templating to "invite inheritors to supply specializations" (Metz) and then use hook methods to allow inheritors to contribute specializations without being forced to use `super`. (Metz)

## Implementation of error messages
"Creating code that fails with reasonable error messages takes minor effort in the present but provides value forever." (Metz)
This template method pattern works but there is an inherent danger in this: if a new `Bicycle` subclass fails to send `super` in one of its messages because a programmer forgot to include `super` when creating that subclass of `Bicycle`, what happens is the resulting messages could result in `nil` values - this makes it very difficult to debug as the returned value of `nil` is not very descriptive. 

Implement error messages for adequate documentation which marks you as a serious programmer. (Metz)

In this case if a size is not implemented in each instantiation, we get a `undefined local variable or method`. While it may be clear to you as a designer the requirements of each subclass - it may not be clear to other programmers in the future. (Metz)

A solution to this can be:
```
def default_tire_size
    raise NotImplementedError
end
```
The benefit to this is that we are explicitly stating that new objects of the `Bicycle` subclass must implement a tire size otherwise, an error message is raised.

Even more specific to this error would be:
```
def default_tire_size
    raise NotImplementedError
            "#{self.class} should have implemented..."
end
```
Which returns a message similar to...`RecumbentBike should have implemented.../some_file.rb:15:in 'default_tire_size'`

## Manage your couplings
Managing coupling is important. Tightly coupled superclasses and subclasses stick together and may be impossible to change independently. (Metz)

Utilizing hook methods allows for looser coupling between the super and sub classes, making that relationship more flexible and therefore much more resilient.

## Was this helpful?

Outdated information? Grammar or spelling errors? Just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com)