---
layout: post
title: Breaking Demeter Explained
categories: [Tech, Backend Engineering, Ruby]
---

# Breaking Demeter

[Breaking Demeter - An obnoxious (and mostly useless) study in the (im)proper selection of nested classes and collections](https://github.com/kon-ham/breaking_demeter)

I had shared this post earlier - but I think it's due for an explanation of what this repo is meant to accomplish.

For context, I was learning to code with Ruby as I was attending Turing School of Software and Design. Other students and myself were having trouble visualizing or understanding how nested collections could be accessed. In order to help deepend our understanding, I created a tutorial on how to do just that - except in the most obnoxious way possible.

Of course, it's not ideal to access one object's attributes if you must go through two or three objects in order to get what you need - if you are doing this you probably could afford to rethink some of your design as doing so is not very Object Oriented Programming-like, hence why we have general design guidelines like the Law of Demeter which suggest that you minimize the amount of reaching through different objects to simply one. One object to reach through another. No more. 

This repo and tutorial is a play-on the name of the Law of Demeter and without shame breaks the Law of Demeter many, many times. 

I justify breaking such a design principle here in order to help learners visualize with `binding.pry` how you could access one object through another, ad nauseum. 

My hope is that at the very minimum, a person going through this test will eventually come to realize that while yes, you can access the attributes of one object by going through three or four different objects, it's obnoxious and not very suited for developer empathy. 

Plus, you miss out on some of the benefits of object oriented programming like being able to abstract out the purpose of an object into more simple objects. (One object, one job.)

I wrote the lesson with the hope of being a short primer into nested collections and objects while injecting a bit of humor into the material in order to keep things relatively interesting.

Hope you enjoy!

[Breaking Demeter - An obnoxious (and mostly useless) study in the (im)proper selection of nested classes and collections](https://github.com/kon-ham/breaking_demeter)

## Was this helpful?
I may have gotten some information incorrect or my grammar might be hard to read. Please let me know.

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)