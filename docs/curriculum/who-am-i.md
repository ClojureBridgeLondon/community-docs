---
layout: curriculum
title: Who Am I
permalink: /docs/curriculum/who-am-i
level: easy
author: jr0cket
---

To start our journey into Clojure, lets be a little introspective and represent ourselves in code.

In this section you will write your first bit of code and learn about using a _string_ in Clojure.

<hr />

## So who are you?

We can write a sentence about ourselves as a _string_.  A string is a collection of characters and is always between double quotes, for example `"I am a string"`.

Lets look at the simplest possible way you could write some information about yourself

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
"John Stevenson, age 21, height 6ft4, blue eyes, dark and brooding"
</code></pre>


## So What is a String?

* A _string_ is a group of characters as a single value
* A _string_ can also be thought of as a collection of characters
* Once you create a string you cannot change it (immutable)

Strings are used in code for things like peoples names and other non-numerical information, such as email & postal addresses.

In the financial world, strings may be used to keep records of transactions, combining to create a history of all the transactions that month on a bank statement.

Strings are also commonly used to keep a log of what your code is doing, especially when there are errors occurring.

> Technical Note: A string is a type and in Clojure that type is `java.lang.String`.  Strings in Java are immutable (cannot be changed when created) so it makes sense to use the Java String type than create a specific one for Clojure.
