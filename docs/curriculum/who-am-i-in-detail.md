---
layout: curriculum
title: Who Am I In Detail
permalink: /docs/curriculum/who-am-i-in-detail
level: easy
author: jr0cket
---

Using what we have just learnt from Clojure Collections, lets define ourselves in more detail using a _vector_ type of collection.

## Vector Collections 

Create a _vector_ using `[ ]` around one or more _values_.

```
[1 2 3 4]
["Its" true "Vectors" "can" "hold" 0 "or" "greater" "values"]
```

A _vector_ is a very flexible box you can put any kind of _values_ in (eg. strings, numbers, characters, function calls, names, true, false, keywords).

There is no limit to the number or types of values you can put into a vector (although an infinite number of values could prove tricky all at once)

You can also create a a vector using the function `vector`

```
(vector 1 2 3 4)
```


## Who am I as a collection

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

Previously you used a string to define information about yourself.  Now lets create a string for each piece of information about yourself

**Using a Vector of Strings and numbers to define yourself**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
[]
</code></pre>

**Give the collection a name using the `def` function**.

By giving a vector a name, we can return the value of that vector by using its name.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details )

my-details
</code></pre>

Here is a [suggested example](https://gist.github.com/3d007ae54f75375ec9d27e953237ecb9)
