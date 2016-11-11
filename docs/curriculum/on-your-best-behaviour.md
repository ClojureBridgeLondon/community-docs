---
layout: curriculum
title: On Your Best Behaviour
permalink: /docs/curriculum/on-your-best-behaviour
level: easy
author: jr0cket
---

In this section you will learn how to define your own simple functions.

We will also introduce the following functions for the first time:

| `fn`   | create an anonymous function, one without a name |
| `defn` | assign a name to a function                      |

<hr />

> FIXME: some duplication in this section, possibly refactor out the anonymous functions to its own page.


## Creating simple math functions

Lets take a simple maths sum, `(+ 1 10)`.  This will add the number `10` to the number `1`, giving the result of `11`.  We have not changed the value of 10 or of 1, instead we created a new value.

If we wanted to add `10` to lots of different numbers, then we can create a function to do this

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
((fn [number] (+ number 10)) 6)
</code></pre>

We create our own function by calling the `fn` function.  The arguments to that function (if there are any) are put into a vector `[ ]`.  Then the behaviour of that function is defined, typically a call to one or more other functions that use the argument.



<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn add-ten
  []
    (+ 1 10))
</code></pre>

Now we can add an _argument_ to the function.  This allows us to add 10 to a different number each time we call the function.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn add-ten
  [number]
    (+ number 10))

(add-ten 3)
</code></pre>

Finally we define the function with two arguments, representing two numbers we are going to add together

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn add-two-numbers
  [number-one number-two]
    (+ number-one number-two))
</code></pre>


## Creating simple behaviour with `fn`

The `fn` function is used to define an anonymous function in Clojure.  An anonymous function is a piece of behaviour you define and use straight away.  As an anonymous function has no name, you cannot call it multiple times, its only used where its defined.

To define an anonymous function as follows

`(fn [optional-parameters] (str "some behaviour" optional-parameters))`

We create our own function by calling the `fn` function.  The arguments to that function (if there are any) are put into a vector `[ ]`.  Then the behaviour of that function is defined, typically a call to one or more other functions that use the argument.

## Calling an anonymous function

To use the anonymous function it needs to be called like any other function, by being the first element in a list or passed to another function that takes a function as an argument.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
((fn [message] (str message)) "An anonymous function that prints its single argument")
</code></pre>


## Creating simple math functions

Lets take a simple maths sum, `(+ 1 10)`.  This will add the number `10` to the number `1`, giving the result of `11`.

**Create an anonymous function to add `10` to a number**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>

Here is a [suggested example](https://gist.github.com/84430932b150f5bf364e1853a058fe07).

## Creating a named function with `defn`

A named function is very similar to an anonymous function, except that a named function can be used many times throughout your code.  A named function is created using the function `defn`

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn my-function
   "This is a string that should document the behaviour of the function"
   [optional-parameters]
   (str "write your behaviour here" optional-parameters))

(my-function "some arguments")
</code></pre>

We have created a named function called `my-function` that takes a parameter.  The function then prints our that paramter, joined with another message using the `str` function.

> Technical Note: The `defn` function is actually a macro in Clojure.  A macro is something that expands into more elaborate code when Clojure reads it.  The `defn` function actually expands to a `def` function that wraps an anonymous function.  Macros are used to extend what you can do with the Clojure language whilst keeping the code as simple as possible.

## Write your own named functions

Lets write some simple named functions.  In the first function we will add two specific numbers, then taking one of the numbers as an argument, finally taking both numbers as arguments.

**Write a named function called `add-ten` to add two numbers together**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn add-ten
  []
  ())

(add-ten)
</code></pre>

Now we can add an _argument_ to the function.  This allows us to add 10 to a different number each time we call the function.

**Write a named function to add 10 to a number given as an argument**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()

;; (add-ten 4)
</code></pre>

**Write a named function to add two numbers, both given as arguments**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()

;; (add-numbers 5 10)
</code></pre>


Here are the [suggested answers](https://gist.github.com/7dc42d57506ab9b82d3016659eaacfa0) for the exercises above.
