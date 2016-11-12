---
layout: curriculum
title: Collections Overview
permalink: /docs/curriculum/clojure-collections
level: easy
author: jr0cket
---

A collection is a programming concept that simply is a container that holds other values.  Put simply a collection is a group of things, where those things can be anything you want to keep together.

Examples of collections you may have yourself in your own live could include:

* your favourites on Netflix or your favourite videos on YouTube
* all the books you own
* a wishlist on Amazon
* the Pokemon you have collected

A collection is often made up of similar things or things that are related to each other in some way.  In some languages collections contain the same types of things, whereas Clojure collections can contain anything, just like cardboard boxes packed in a hurry on the day you move house.

Collections in Clojure can contain any valid Clojure value or expression (`"string"`, `99`, `3/4`, `(str "function call")`)

<hr />

## Collections in Clojure

We have already seen a String in the previous section.  This is a very simple form of collection which can only contain characters.

In this section you will learn about some of the collections available in Clojure that help you group things together.

There are 4 other collections that are very useful within Clojure

| List            | `()`     | A list of things that are accessed one after another (linked list).  The first element of a list is a function call unless wrapped by the `quote` function |
| Vector          | `[]`     | A group of things that can be access by there position in the collection (indexed array)                                                                   |
| Map             | `{}`     | One or more pairs of keys and values (hash map).  Keys are used to find specific values                                                                    |
| Set             | `#{}`    | A unique collection of things.  No two things can be identical                                                                                             |


## Common functions for Collections

There are several functions that help you get information out of collections and these functions work on all the different types of collections.

The functions `first`, `second`, `next`, `last`, `rest`,`nth` all return a value at a given place in the collection.

The functions `get` and `get-in` will get value that are paired with the given value.  We will see more of this when using map collections.


## Differences between Collections

In almost all contexts, you can consider vectors, lists, and other sequences as interchangeable. They only differ in their performance characteristics and in a few data-structure-specific operations.

You can also consider lists and vectors equal if they have the same values in them.  For example:

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(= (list 1 2 3 4) (vector 1 2 3 4))
</code></pre>
