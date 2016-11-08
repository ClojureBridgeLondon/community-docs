---
layout: curriculum
title: What's in a name
permalink: /docs/curriculum/whats-in-a-name
level: easy
author: jr0cket
---

In this section you will learn about assigning (binding) names to values.

We will introduce the following functions for the first time:

| `def`    | assign a name to a value (a value being a number, string, collection or function) |
| `str`    | join values together to form a single string                                      |

<hr />


## Give yourself a name with `def`

The function `def` can be used to give a name to something, or more specifically we are defining a name for a value.  For example, you can give a name to a string or number and most other things in Clojure.

**Define a name that contains a string of your name (or any name you prefer)**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-name "John Stevenson")
</code></pre>

> Once you define a name on a page, that name can be used with any other code on the same page


## Using names

To get the value of a name you can simply use the name in your code

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
my-name
</code></pre>


## Define names for other things

You can define names for many things in your code.  By giving a name to something, it makes it very easy to use those things elsewhere in your code just by using the name.

Using the `def` function to give a name to something means that you only need to change your code in one place, in the `def` function and your code will use the new version.

**Define other information about yourself (this information doesn't need to be true)**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
;; (def my-preferred-age 25)
;; (def favourite-language "Clojure")
;; (def my-group ["Tina" "Belinda" "Harmony"])
</code></pre>


## The `str` function

The `str` function is used to join strings together, returning a new string as the result.  The `str` function can also be used to join other values, such as numbers, where those numbers are made part of the new string that is returned

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(str "I can" " " "join strings" " " "and other values" " " "together")
;; (str "I can join" " " 1 " " "or more string")
;; (str "I return" " " 1 " " "string as a result")
</code></pre>

## Using names with functions

Its much more common to use a name with a function, rather than just using the name by itself.

**Join names you defined with another String**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(str my-name " is enjoying coding in Clojure")
</code></pre>
