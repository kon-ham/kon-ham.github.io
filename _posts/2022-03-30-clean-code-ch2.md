---
layout: post
title: Summary of "Clean Code", Ch. 2
---
This is a summary of Martin's "Clean Code". That means there is no idea here that is original to my own - I am summarizing the material for my learning and in case you might want a quick summary. In fact there are points here where I completely copy word for word what tue author has said. I take no credit. All credit goes to Martin.

Names need to have purpose - they must reveal their intent. These names should tell you why it exists, what it does, and how it is used. If a name requires a comment, that name does not reveal its intent.

Understanding that names are important, the problem is not simply the simplicity of the code but rather the *implicity* of the code. (Martin)

For example, if your name refers to an `AccountList` and it does not actually contain a `List` then this can cause confusion. The English understanding of a list is not the same as the programming understanding of a `List`. Be aware of names that vary in small ways. Consider `XYZControllerForEfficientHandlingOfStrings` as opposed to `XYZControllerForEfficientStorangeOfStrings` - notice that the shapes of these names are similar and these can cause confusion.

Understand the context for which a programmer might be coming across either of the above variables. Programmers use auto-complete at times and a programmer can very easily pick one over the other.

Consider how you might use `O` versus `0` or `l` (L) versus `1`. These are very confusing to the reader and adds friction to the reading process. You may need to assign names to many individual objects - be mindful to make meaningful distinctions. Resist the temptation to create distinctions only to satisfy the compiler.

Number-naming series are the opposite of intentional meaning. (`a1, a2, a3, a4, a5`)They are non-informative. They provide no clue to the author's intention.

Vague naming for a `Product` class like `ProductInfo` or `ProductData`, in particular words like 'info' and 'data' are noise words. They are indistinct such as 'a', 'an', and 'the'. (Martin)

As you think about naming conventions and similar words, classes, objects, variables, think about how naming one object provides *distinction* to the person reading your code.
-
  ```
  getActiveAccount();
  getActiveAccounts();
  getActiveAccountInfo();
  ```
An example of naughtiness. Make sure the naming allows for meaningful distinguishing of one name over the other.

If you cannot pronounce the names you decide, reconsider it. `DtaRcrd102` pronounced is 'dee-ta-er-cerd-won-oh-two'. Make sure your names are easy to search. Naming your object `2390849032` is not very easily searchable as mistakes can happen in transcribing it over elsewhere to search. Single word names are just as difficult to search.

Martin likes to consider the length of names based on the scope of the thing being called. He prefers to use single-letter names only within the scope of a local variable. If your variable or constant is being used or referenced many times it should be given a name that is easily searchable.

Class names should have nouns. `Customer`, `WikiPage`. It should not be a verb. Avoid usage of `Data`, `Info`, `Manager` as these words come with baggage. Method names should be verbs or verb phrases. "Accessors, mutators, predicates should be named for their value prefixed with `get`, `set`, and `is`.

Don't go for humor or cute. It's not appropriate.

If you can, try to be consistent with themes or concept. If you have a `DeviceManager` and a `Protocol-Controller` why not fix both with `Manager` or `Controller`? `DeviceManager` and `ProtocolManager` is much more consistent.

Don't use the same word for two different purposes, which Martin says is essentially a "pun".

We want our code to be a quick skim. Not an intense study. (Martin)

Write your names so that they are "solution domains", not "problem domains". If your programmer has to go back to the customer to understand what a word is, that is a problem. Instead focus on using terminology that focuses on the solution. If you cannot use a solution domain name, use a problem domain name, since this is better than having no context at all.

Make sure the context is meaningful at all times. If you have variables `name, city, state` then it makes sense what `state` is referring to. What if `state` was on its own? This then becomes confusing.

Shorter names are better than longer ones, so long as they are clear. Add no more context than necessary. Be precise.
The challenge is in being descriptive while understanding cultural background.

## Was this helpful?

Outdated information? Grammar or spelling errors? Just want to chat?

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com)