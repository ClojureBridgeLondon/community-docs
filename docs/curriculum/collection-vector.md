---
layout: curriculum
title: Collection - Vector
permalink: /docs/curriculum/collection-vector
level: easy
author: jr0cket
---

A _vector_ is a very flexible and easy to use collection type, so it is very common and often the default choice for holding information.

We have seen how to define a _vector_ using the square brackets `[ ]` notation.  You can also create a vector using the function `vector` as well as convert another collection to a vector using the `vec` function.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(vector 1 2 3)
;; (vec (list 1 2 3))
</code></pre>


## Getting values from a vector

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

Our friends first, second, and nth work here too; but unlike lists, nth is fast on vectors. That’s because internally, vectors are represented as a very broad tree of elements, where each part of the tree branches into 32 smaller trees. Even very large vectors are only a few layers deep, which means getting to elements only takes a few hops.

**Get a value from a vector by its position**

Use the functions `first`, `second`, `last` and `rest` to get values from a vector collection.  Each function takes a collection as an argument.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">

</code></pre>

[examples](https://gist.github.com/72a00ca49d60b16bbde263b0e76d33fc)


## Looking up values in a specific position

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

A vector is _indexed_, meaning that each of the values are assigned a number in the order they are in the vector.  Indexes start at zero, rather than one.

The `nth` function takes a vector and a position in the index and returns the value at that position

```
(nth ["Jane Doe" 162 "Clojure"] 0)
```

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def jane ["Jane Doe" "age 21" "height 163" "loves Clojure"])
</code></pre>

**Get a value from the vector called Jane using `nth`**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">

</code></pre>


## Counting the number of values in a vector

The function `count` will return the number of values in a collection.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(count [1 2 3])
</code></pre>


### Adding values to a vector

Using the `conj` function on a vector adds a value to the end, not the start

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(conj [1 2 3] 4)
</code></pre>

> FIXME: move adding values to a vector to a separate section

## Vectors are equal when values are equal

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

Finally, note that vectors containing the same elements are considered equal in Clojure.

**Take a guess as to if the following are equal**

```
(= [1 2 3] [1 2 3])
(= [1 2 3] [4 5 6])
(= ["Hello" "World"] ["Hello" "World" "Wide" "Web"])
(= '(1 2 3) [1 2 3])
```

If any line above is equal, it will return true when pasted into the code box below

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">

</code></pre>
