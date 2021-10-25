---
layout: post
title: The (Super Short) Difference Between P, Puts, Print, and Return
---

### Summary:
Use `p` if you need your output to look more closely to what your Ruby code looks like.

Use `puts` if you need to output your value *and* create a new line afterwards. You'll notice in the example below `puts` does not literally output values in our array example.

Use `print` if you need to output your value *with no new line*.

Use `return` if you need to simply return a value without indicating a need for a visible output for your value.

Here's an example of an output:

    ```
    irb(main):001:0> array = ["chicken", "butt", " ", nil, 9001]
    => ["chicken", "butt", " ", nil, 9001]

    # Using p
    irb(main):002:0> p array
    ["chicken", "butt", " ", nil, 9001]
    => ["chicken", "butt", " ", nil, 9001]

    # Using puts
    irb(main):003:0> puts array
    chicken
    butt


    9001
    => nil

    # Using print
    irb(main):004:0> print array
    ["chicken", "butt", " ", nil, 9001]=> nil
    ```

*If* you are still confused about specific use cases for each of these I would encourage you not to worry about it. You can use this for reference later and if you have a specific use-case you need, try to figure it out then.

What's really important to know between all of these methods is that they're similar but not the same.

## Was this helpful?
I may have gotten some information incorrectly or my grammar might be hard to read. Please let me know.

Contact me at [info.konham@gmail.com](mailto:info.konham@gmail.com) or [contact@konkham.com](mailto:contact@konkham.com)