---
layout: curriculum
title: Who Are We
permalink: /docs/curriculum/who-are-we
level: easy
author: jr0cket
---

Lets define some information about the group we are part of at ClojureBridge.  Change the examples in this section and represent the people in your own group.

In the previous section we defined ourselves as a collection, something like the following.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details ["John Stevenson" "37" "Clojure" "London" "North Yorkshire" 12])

my-details
</code></pre>

We also defined simpler definitions to hold just our name

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-name "John Stevenson")

my-name
</code></pre>

> Hint: We can use both of these definitions in the next exercises.

## So who are we?

We can also use a Clojure collection to hold lots of values about the group we are in.

**Define the group you are in**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-group ["John Stevenson" "Rich Hickey" "Chris Howe-Jones" "Bruce Durling"])
</code></pre>

**Try Nesting Collections so you can include even more information**

As we already defined `my-name` as a name that points to my full name, we can use `my-name` as part of the collection for `my-group`

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-group [my-name "Rich Hickey" "Chris Howe-Jones" "Bruce Durling"])
</code></pre>

> Remember: Any names we define in this page will be available to any sections of code after the definition of that name.

**Try defining more details about your group using vectors within vectors**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-group
  [my-name
   ["Rich Hickey" 42 "Clojure" "New York" "New Mexico" 10]
   ["Chris Howe-Jones" 59 "Cobol" "London" "Newcastle" 10]
   ["Bruce Durling" 72 "Erlang" "London" "North Yorkshire" 13]])
</code></pre>

The name `my-name` is already associated with a vector collection containing my details, so its not neccessary to put `my-name` in a vector.



## Getting information from collections

> FIXME: Move content to its own page

Collections are very common in Clojure, so there are quite a lot of functions that let you do things with the information inside collections.

Lets look at the most commonly used functions to get information out of collections.

**Uncomment each line in turn to see what each function returns**

~~~klipse
(first my-details)

;; (second my-details)

;; (last my-details)

;; (rest my-details)
~~~

In this little exercise, we would like to send a letter a letter to a person who's name is in the `my-details` collection.  We want to get the first name and then just the initial of the first name.

**Using `my-details` as the collection, get the first character of the first name**

~~~klipse
()
~~~

> Hint: Functions return a value, so you can always use that value with another function.


## Limitations of Vector collections

Once of the disadvantages of a _vector_ is ambiguity.  Just by looking at the vector its not always obvious as to what each value represents.

For example, we can infer that "John" and "Stevenson" are probably the persons first and last names.  However, is this person's age 37 or is it 12.  If that person is aged 37 then what does the 12 represent.  Is it they years they have lived in London, is it the age they left North Yorkshire or is it simply their shoe size






## Giving meaning to data with maps

> FIXME: Move this content to is own page

Another common collection in Clojure is a _map_.  A map is a collection that contains pairs of keys and values.  The keys allow you to look up the values in a map.

~~~klipse
{"key" "value"}

;; {1 "air" 2 "light" 3 "heat"}

;; {"a" "sit down" "b" "switch on laptop" "c" "get coding"}

;; {"language" "Clojure" "event" "ClojureBridge London" "website" "clojurebridgelondon.github.io"}
~~~

These examples show how we can use a map to define something with meaning, the keys providing the context for the values of the map.

### Keywords

Its quite common to a _keyword_ for the keys in maps.  A keyword always starts with a colon, `:`.  Keywords are different to names because they point to themselves rather than another value, so they do not need to be defined with `def`.  Keywords have a unique identity in your code and this allows you to find a keyword in any collection just by using its name.

Lets take one of the previous examples and replace the keys with keywords

~~~klipse
{:language "Clojure" :event "ClojureBridge London" :website "clojurebridgelondon.github.io"}
~~~

> Note: Keywords give us some additional power that we will cover at the end of this section.  In the current examples they are just making it a little easier to distinguish the keys from the values in a map.  Although you can also use keywords as values too.


### Exercise: We are Groot

> FIXMe: Create a challenge for this

Define information about the group you are in using a _map_, using Clojure _keywords_ as the keys of the map and strings or numbers for the values.

Remember that a valid map must have a key and a value as a pair.  You can have multiple key-value pairs in a map.

~~~klipse
{:teamname "awesome" :members ",,,"}
~~~
