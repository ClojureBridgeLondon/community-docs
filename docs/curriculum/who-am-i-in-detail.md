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


## What is a Vector

A _vector_ is a very flexible and easy to use collection type, so it is very common and often the default choice for holding information.

We have seen how to define a _vector_ using the square brackets `[ ]` notation.  You can also create a vector using the function `vector` as well as convert another collection to a vector using the `vec` function.

Here are a few examples

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(vector 1 2 3)
;; (vec (list 1 2 3))
</code></pre>


### Getting values from a vector

Our friends first, second, and nth work here too; but unlike lists, nth is fast on vectors. That’s because internally, vectors are represented as a very broad tree of elements, where each part of the tree branches into 32 smaller trees. Even very large vectors are only a few layers deep, which means getting to elements only takes a few hops.




<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(first [1 2 3])

;; In addition to first, you’ll often want to get the remaining elements in a collection. There are two ways to do this:
;; (rest [1 2 3])
;; (next [1 2 3])


;; rest and next both return “everything but the first element”. They differ only by what happens when there are no remaining elements:
;; (rest [1])
;; (next [1])

;; We can get the final element of any collection with last:
;; (last [1 2 3])

;; And figure out how big the vector is with count:
;; (count [1 2 3])

;; Because vectors are intended for looking up elements by index, we can also use them directly as verbs:
;; ([:a :b :c] 1)
;; So we took the vector containing three keywords, and asked “What’s the element at index 1?” Lisp, like most (but not all!) modern languages, counts up from zero, not one. Index 0 is the first element, index 1 is the second element, and so on. In this vector, finding the element at index 1 evaluates to :b.

;; Finally, note that vectors and lists containing the same elements are considered equal in Clojure:
;; (= '(1 2 3) [1 2 3])

</code></pre>

rest returns logical true, next returns logical false. Each has their uses, but in almost every case they’re equivalent–I interchange them freely.


### Adding values to a vector

Using the `conj` function on a vector adds a value to the end, not the start

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(conj [1 2 3] 4)
</code></pre>
