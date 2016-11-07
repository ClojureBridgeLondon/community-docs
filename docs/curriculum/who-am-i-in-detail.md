---
layout: curriculum
title: Who Am I In Detail
permalink: /docs/curriculum/who-am-i-in-detail
level: easy
author: jr0cket
---

Using what we have just learnt from Clojure Collections, lets define ourselves in more detail using a _vector_ type of collection.

## Who am I as a collection

First lets start with defining ourselves in a bit more detail (again, none of this had to be real information about you).

Using the square brackets,`[ ]` represents a _vector_ in Clojure.  A _vector_ is a very flexible box you can put any kind of _values_ in (strings, numbers, characters, function calls, names, true, false, keywords).

There is no limit to the number or types of values you can put into a vector (although an infinite number of values could prove tricky all at once)


**Using a Vector of Strings to define yourself in more detail**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
["John" "Stevenson" "37" "Clojure" "London" "North Yorkshire" 12]
</code></pre>

We can also give the collection a name using the function called `def`.  If we use the name we have defined for the collection on a line by itself, then Clojure will return the collection.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details ["John Stevenson" "37" "Clojure" "London" "North Yorkshire" 12])

my-details
</code></pre>


