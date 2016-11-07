---
layout: curriculum
title: Looking up values in Maps
permalink: /docs/curriculum/looking-up-values-maps
level: easy
author: jr0cket
---

We have created several collections already, but how do we use the information in those collections.  Howe do we pull out just the specific parts parts we want from those collections.  We will answer these questins in this section

In this section you will learn more about the functions that can be used to access data in collections.  We will also introduce the following functions for the first time:

| `get`, `get-in` | get values from a collection |

> Remember:  If you want to use a collection you define later on in the page then give that collection aname using the function `def`.  Then you can work with that collection just by using its name.

<hr />

## Finding information in maps

Maps and Vectors can be used to create a much more involved structure to your information, allowing you to represent much more complex things.

In this example we model someones very extensive Star Wars collection.

> FIXME:  Make a simpler starwars collection as and example then ask the students to create something more invovled as an exercise in a challenge section

~~~~klipse
(def starwars-characters
  {:jedi   ["Luke Skywalker"
            "Rey"]
   :droids ["R2D2"
            "BB-8"]})
~~~

By typing the name assigned to our map, the map will be returned as the result

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
starwars-characters
</code></pre>


Using the `get` function we can pull out more specific values from the map.  We give the `get` function the map we want to extract a value from and the key that is paired with the value.


~~~klipse
(get starwars-characters :jedi)
~~~


## A more detailed collection

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


The key we use to get values from a map is at the top level, ie. it is not nested in another map.

If we want to get a nested value we can use a variation of the `get` function called `get-in`.  The `get-in` function takes the map and a vector of keys.

**Evaluate each of the functions by un-commenting them in turn**

~~~klipse
(get-in starwars-collection [:characters :jedi])

;; (get-in starwars-collection [:ships :rebels])
~~~


## A little short-cut with keywords

In these most recent examples, the keys used in the map have been defined using the Clojure `keyword` type.  A keyword is most commonly used to find values in a collection, especially maps.

You can also use a keyword as a function, instead of the `get` function.

You can also call a map as if it was a function by using a key as an argument to calling the map as a function.

**Try calling each of the functions at the end of this code snippet**

~~~klipse
(starwars-collection :characters)
;; (:characters starwars-collection)

;; (:ships (starwars-collection :rebels))
;; ((starwars-collection :ships) :rebels)
~~~

If you dont get the use of maps and keywords like this, dont worry.  Just try to see that this is a short-hand version of the `(get map keyword)` function call.
