---
layout: post
title: The (Super Short) Difference Between P, Puts, Print, and Return
---
## Using `p`
* Use `p` if you need your output to look more closely to what your Ruby code looks like.

## Using `puts`
* Use `puts` if you need to output your value *and* create a new line afterwards. You'll notice in the example below `puts` does not literally output values in our array example.

## Using `print`
* Use `print` if you need to output your value *with no new line*.

## Using `return`
* Use `return` if you need to simply return a value without indicating a need for a visible output for your value. Be advised: If your return statement is true and you have multiple lines of code or conditionals, Ruby will execute the first `return` statement that is true. We can sometimes think of `return` statements as being useful for executing edge cases. 

Here's an example of an output:

    ```
    # Defining our array variable
    irb(main):001:0> array = ["chicken", "butt", " ", nil, 9001]

    => ["chicken", "butt", " ", nil, 9001]

    # Using p
    irb(main):002:0> p array
    ["chicken", "butt", " ", nil, 9001]

    # Your output using p
    => ["chicken", "butt", " ", nil, 9001]

    # Using puts
    irb(main):003:0> puts array

    # Your output using puts
    chicken
    butt


    9001
    => nil

    # Using print
    irb(main):004:0> print array

    # Your output using print
    ["chicken", "butt", " ", nil, 9001]=> nil
    ```

## Still Confused?
I would encourage you not to worry about it. You'll get more solid on your understanding when you have a need for it on a case-by-case basis.

What's really important to know between all of these methods is that they're *similar* but *not the same*.

## Was this helpful?
I may have gotten some information incorrect or my grammar might be hard to read. Please let me know.

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)