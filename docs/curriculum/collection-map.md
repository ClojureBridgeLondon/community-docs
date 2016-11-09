---
layout: curriculum
title: Collection - Map
permalink: /docs/curriculum/collection-map
level: easy
author: jr0cket
---

In this section you will learn about the Collection type _Map_.

We will also introduce the following functions for the first time:

| `fn`   | create an anonymous function, one without a name |
| `defn` | assign a name to a function                      |

<hr />


## Limitations of Vector collections

One of the disadvantages of a _vector_ is ambiguity.  Just by looking at the contents of a vector, as in our previous examples, its not always obvious as to what each value represents.

For example, we can infer that "John" and "Stevenson" are probably the persons first and last names.  However, is this person's age 37 or is it 12.  If that person is aged 37 then what does the 12 represent.  Is it they years they have lived in London, is it the age they left North Yorkshire or is it simply their shoe size


## Giving meaning to data with maps

Another common collection in Clojure is a _map_.  A map is a collection that contains pairs of keys and values.  The keys allow you to look up the values in a map.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
{"key" "value"}

;; {1 "air" 2 "light" 3 "heat"}

;; {"a" "sit down" "b" "switch on laptop" "c" "get coding"}

;; {"language" "Clojure" "event" "ClojureBridge London" "website" "clojurebridgelondon.github.io"}
</code></pre>

These examples show how we can use a map to define something with meaning, the keys providing the context for the values of the map.

### Keywords

Its quite common to a _keyword_ for the keys in maps.  A keyword always starts with a colon, `:`.  Keywords are different to names because they point to themselves rather than another value, so they do not need to be defined with `def`.  Keywords have a unique identity in your code and this allows you to find a keyword in any collection just by using its name.

Lets take one of the previous examples and replace the keys with keywords

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
{:language "Clojure" :event "ClojureBridge London" :website "clojurebridgelondon.github.io"}
</code></pre>

> Note: Keywords give us some additional power that we will cover at the end of this section.  In the current examples they are just making it a little easier to distinguish the keys from the values in a map.  Although you can also use keywords as values too.


