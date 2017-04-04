---
layout: curriculum
title: I Like My Clojure Filtered
permalink: /docs/curriculum/i-like-my-clojure-filtered
level: easy
author: jr0cket
---

There are many ways we can process information both as individual values and as collections of values.  

In this section we will introduce the following functions:

* `filter` - 
* `when`, `and`, `or` - make a decision based on some condition
* `odd?`, `even?` - test if a value is odd or even and returns true or false (predicates)
* `for` - loop through values
* `range` - generate a range of numbers

<hr />


## Filtering information

Another form of decision making is to filter information to only return those parts you are interested in, based on some kind of criteria.  A simple example of this is to return all the even numbers from a collection

~~~klipse
(filter even? (range 10))
~~~

There are several functions you can use to filter values, such as `odd?`, `even?`, `true?`, `false?`, `string?`, `integer?`



## Other decision making functions



### When

~~~klipse
(when (> 3 2)
      "Higher")
~~~


### While

> FIXME: needs a better example

    (while test & body)

Repeatedly executes body while test expression is true. Presumes
some side-effect will cause test to become false/nil. Returns nil


<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">

;; a var to be used for its side effects
(def a (atom 10))
;; #'user/a

(while (pos? @a) (do (println @a) (swap! a dec)))
</code></pre>




## Filtering information based on decisions or conditions

Decisions are commonly made when processing information

odd?
even?

~~~klipse
(for [x (range 10) :when (odd? x)] x)
~~~

In the above code, try changing the function `odd?` to the function `even?`.

> Using a ? character at the end of a functions name is a convention used in Clojure.  Functions named in this way should return a true or false answer.  Functions named this way are called a [predicate](https://en.wikipedia.org/wiki/Predicate_(mathematical_logic)).



