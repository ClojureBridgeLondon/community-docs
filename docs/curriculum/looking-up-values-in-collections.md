---
layout: curriculum
title: Looking up values in Collections
permalink: /docs/curriculum/looking-up-values-collections
level: easy
author: jr0cket
---

We have created several _string_ and _vector_ collections already, but how do we use the information in those collections.  How do we pull out just the specific parts parts we want from those collections.  We will answer these questions in this section

In this section you will learn more about the functions that can be used to access data in collections.  We will also introduce the following functions for the first time:

| `first`, `second`, `next`, `last`, `rest`,`nth` | get values from a collection base on position |

> Remember:  If you want to use a collection you define later on in the page then give that collection aname using the function `def`.  Then you can work with that collection just by using its name.

<hr />

## Getting information from collections

Collections are very common in Clojure, so there are quite a lot of functions that let you do things with the information inside collections.

Lets look at the most commonly used functions to get information out of collections.

**Uncomment each line in turn to see what each function returns**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details ["John" "Stevenson" "37" "Clojure" "London" "North Yorkshire" 12])

(first my-details)

;; (second my-details)

;; (last my-details)

;; (rest my-details)
</code></pre>



In the following exercises, we would like to send a letter to a person who's name is in the `my-details` collection.  We want to get the first name and then just the initial of the first name.

**Using `my-details` as the collection, get the first character of the first name**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>

**Using `my-details`, now get the first character of the first name**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>

> Hint: Functions return a value, so you can always use that value with another function.

Once you have completed the exercises, see the [suggested examples](https://gist.github.com/f552382d8c4e6ddedaf7eeecf01800e3)
