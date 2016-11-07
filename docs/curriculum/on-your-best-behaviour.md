---
layout: curriculum
title: On your best behaviour
permalink: /docs/curriculum/on-your-best-behaviour.md
level: easy
author: jr0cket
---

In this section you will learn how to define your own simple functions. 

We will also introduce the following functions for the first time:

| `fn`                         | create an anonymous function, one without a name |
| `defn`                       | assign a name to a function                      |

<hr />






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
