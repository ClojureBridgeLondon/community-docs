---
layout: curriculum
title: Looking up values in Maps
permalink: /docs/curriculum/looking-up-values-in-maps
level: easy
author: jr0cket
---

In this section you will learn more about the functions that can be used to access data in collections, specifically in _maps_.  We will also introduce the following functions for the first time:

| `get`, `get-in` | get values from a collection based on a key |

> Remember:  If you want to use a collection you define later on in the page then give that collection aname using the function `def`.  Then you can work with that collection just by using its name.

<hr />

## Collections as maps

We have seen in previous sections how maps can be used to create a much more involved structure to your information, allowing you to represent much more complex things.

In this example we model someones very basic Star Wars collection.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def starwars-characters
  {:jedi   ["Luke Skywalker"
            "Rey"]
   :droids ["R2D2"
            "BB-8"]})

starwars-characters
</code></pre>


## Finding information in maps

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

Using the `get` function we can pull out more specific values from the map.  We give the `get` function the map we want to extract a value from and the key that is paired with the value.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(get starwars-characters :jedi)
</code></pre>


**Get the droids from the starwars-characters collection**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>



## A more detailed collection

Here is an example of a more detailed collection, where some of the values in the map are maps themselves.  So instead of `{key value}` we have `{key {key value}}` or even `{key (key {key value})}`.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def starwars-collection
  {:characters {:jedi   ["Luke Skywalker"
                         "Rey"]
                :droids ["R2D2"
                         "BB-8"]}
   :ships {:rebels ["Millenium Falcon"]}})

starwars-collection
</code></pre>

> Hint: You may have noticed that the values are actually a vector of values.  We can use any collection as our value.

## Getting values from nested maps

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

In the previous example the key we use to get values from a map was at the top level, ie. it is not nested in another map.

If we want to get a nested value we can use a variation of the `get` function called `get-in`.  The `get-in` function takes the map and a vector of keys.

`(get-in map [keys])`


**Get all the jedi characters**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>

You could use the `get` function twice: `(get (get starwars-collection :characters) :jedi)`.  Its more common to use the `get-in` function when there are nested maps though.

**Get all the ships that belong to the rebels**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>

Once you have completed the exercises, take a look at the [suggested examples](https://gist.github.com/3a7be833cb581c36adb463e1498e54a0)

<hr />

## A little short-cut with keywords

In these most recent examples, the keys used in the map have been defined using the Clojure `keyword` type.  A keyword is most commonly used to find values in a collection, especially maps.

You can also use a keyword as a function, instead of the `get` function.

You can also call a map as if it was a function by using a key as an argument to calling the map as a function.

**Uncomment each line in turn to compare to previous examples**

~~~klipse
(starwars-collection :characters)
;; (:characters starwars-collection)

;; (:ships (starwars-collection :rebels))
;; ((starwars-collection :ships) :rebels)
~~~

If you dont get the use of maps and keywords like this, dont worry.  Just try to see that this is a short-hand version of the `(get map keyword)` function call.
