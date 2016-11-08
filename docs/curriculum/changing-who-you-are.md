---
layout: curriculum
title: Changing who you are
permalink: /docs/curriculum/changing-who-you-are
level: easy
author: jr0cket
---

We can change things in many ways in Clojure, however most of the time it looks like we change things, we are merely making new things from the old ones.  For example, when we add two numbers we dont actually change either number, instead we create a third number that is the result.

In this section you will learn about how to change things, first by using existing parts of Clojure, then by writing your own behaviour.  When we define our own behaviour we can wrapping it up in function and give that function a name.

The functions from Clojure and the ones we create ourselves will be used with the collections from the previous section.

We will also introduce the following functions for the first time:

* `defn` - assign a name to a function

<hr />

> FIXME: The following should be a section on simple maths

## Simple addition

You can use existing functions by putting the name of the function as the first thing in a list, `()`.

Lets do some simple math

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(+ 1 2)
</code></pre>


<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(+ )

;; (- )
;; (* )
;; (/ )
;; (< )
;; (> )
</code></pre>



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



<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn add-two-numbers
  [number-one number-two]
    (+ number-one number-two))
</code></pre>
