---
layout: curriculum
title: Reference: Clojure Collections Introduction
permalink: /docs/curriculum/clojure-collections
level: easy
author: jr0cket
---

A common way to organise groups of information is to use a Collection.  Examples of collections you may already include all the music you own, your favourite videos on YouTube, all the Pokemon you have collected, etc.

Put simply, a collection is a box of things, where the things can be anything you want to keep together.

In this section you will learn about some of the collections available in Clojure that help you group things together.

We will also introduce the following functions for the first time:

* `first`, `second`, `last`, `rest`, `get`, `get-in` - get values from a collection

> Remember:  If you want to use a collection you define later on in the page then give that collection aname using the function `def`.  Then you can work with that collection just by using its name.

<hr />

## Reference: Collections in Clojure 

We have already seen a String in the previous section.  This is a very simple form of collection which can only contain characters.

There are 4 other collections that are very useful within Clojure 

| Collection name | Notation | Description                                                                                                                                                |
|-----------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| List            | `()`      | A list of things that are accessed one after another (linked list).  The first element of a list is a function call unless wrapped by the `quote` function |
| Vector          | `[]`      | A group of things that can be access by there position in the collection (indexed array)                                                                   |
| Map             | `{}`      | One or more pairs of keys and values (hash map).  Keys are used to find specific values                                                                    |
| Set             | `#{}`     | A unique collection of things.  No two things can be identical                                                                                             |

### Examples of Collections

A collection is a common programming concept that simply is a container that holds other values.

Examples of collections in your life could be your CD collection, your Spotify lists of music, or your wish list of things you want to buy on Amazon.

A collection is often made up of similar things or things that are related to each other in some way.  In some languages collections contain the same types of things, whereas Clojure collections can contain anything, just like cardboard boxes packed in a hurry on the day you move house.

Collections in Clojure can contain any valid Clojure value or expression (`"string"`, `99`, `3/4`, `(str "function call")`).

