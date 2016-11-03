#---
layout: curriculum
title: Challenge: Making a Meal of It
permalink: /docs/curriculum/making-a-meal-of-it
level: easy
author: jr0cket
---

Lets be a little introspective and represent ourselves and other groups of things in Clojure code

In this section you will learn about collections, such as _string_, _vector_ and _map_.  We will also introduce the following functions for the first time:

* `def` - assign a name to a value (a value being a number, string, collection or function)
* `str` - join the arguments together to form one string
* `first`, `second`, `last`, `rest`, `get`, `get-in` - get values from a collection

<hr />

# Describing more complex things

In the previous section we have represented ourselves as a fairly simple structure, just as a collection of values, mainly strings and numbers.

We can also include collections as elements in a collection.

~~~klipse
["my-friends" ["Kerry" "Chris" "Abby"]]

;; {:types-of-pet ["cat" "dog" "tropical fish" "rabbit"] }

;; {:bicycle ["wheels" "frame" "handlbars"]}
~~~
