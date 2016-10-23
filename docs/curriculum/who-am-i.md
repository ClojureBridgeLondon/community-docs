---
layout: curriculum
title: Who Am I
permalink: /docs/curriculum/who-am-i
level: easy
author: jr0cket
---

Lets be a little introspective and represent ourselves and other groups of things in Clojure code

In this section you will learn about collections, such as _string_, _vector_ and _map_.  We will also introduce the following functions for the first time:

* `def` - assign a name to a value (a value being a number, string, collection or function)
* `str` - join the arguments together to form one string
* `get`, `get-in` - get values from a collection

<hr>

## So who are you?

We can write a sentence about ourselves as a _string_.  A string is a collection of characters and is always between double quotes `"Your string goes here"`.

Lets look at the simplest possible way you could write some information about yourself

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
"John Stevenson, age 21, height 6ft4, blue eyes, dark and brooding"
</code></pre>

We could also use a Clojure collection to hold lots of values about ourselves.

Using the square brackets,`[ ]` represents a _vector_ in Clojure.  A _vector_ is a very flexible box you can put any kind of _values_ in (strings, numbers, characters, function calls, names, true, false, keywords).

There is no limit to the number or types of values you can put into a vector (although an infinite number of values could prove tricky all at once)

> Note: a vector is often used in Clojure as its such a flexible and easy to use collection.

~~~klipse
["John" "Stevenson" "37" "Clojure" "London" "North Yorkshire" 12]
~~~

Once of the disadvantages of a _vector_ is ambiguity.  Just by looking at the vector its not always obvious as to what each value represents.

For example, we can infer that "John" and "Stevenson" are probably the persons first and last names.  However, is this person's age 37 or is it 12.  If that person is aged 37 then what does the 12 represent.  Is it they years they have lived in London, is it the age they left North Yorkshire or is it simply their shoe size

## Using Maps to give meaning to data

Another common collection in Clojure is a _map_.  A map is a collection that contains pairs of keys and values.  The keys allow you to look up the values in a map.


> Note: If you have ever seen a json file you may recognise the similarities in structure

### Exercise

Define information about yourself using a _map_, using Clojure _keywords_ as the keys of the map and strings or numbers for the values.

Remember that a valid map must have a key and a value as a pair.  You can have multiple key-value pairs in a map.

~~~klipse
{:firstname "John" ,,, ,,,}
~~~


## Maps and vectors

Maps and Vectors can be used to create a much more involved structure to your information, allowing you to represent much more complex things.

In this example we model someones very extensive Starwars collection.

We have created a map

~~~klipse
(def starwars-collection
  {:characters {
                :jedi   ["Luke Skywalker"
                         "Obiwan Kenobi"
                         "Quigon Gin"
                         "Rey"]
                :sith   ["Darth Vader"
                         "Darth Sideous"]
                :droids ["C3P0"
                         "R2D2"
                         "BB-8"]}
   :ships {
           :rebel-alliance  ["Millenium Falcon"
                             "X-wing fighter"]
           :imperial-empire ["Death Star"
                             "Intergalactic Cruiser"
                             "Star Destroyer"
                             "TIE Fighter"
                             "Lambda-class Shuttle"]}})

;; By typing the name assigned to our map, the map will be returned as the result
starwars-collection
~~~

Using the `get` function we can pull out more specific values from the map.  We give the `get` function the map we want to extract a value from and the key that is paired with the value.


~~~klipse
(def starwars-collection
  {:characters {
                :jedi   ["Luke Skywalker"
                         "Obiwan Kenobi"
                         "Quigon Gin"
                         "Rey"]
                :sith   ["Darth Vader"
                         "Darth Sideous"]
                :droids ["C3P0"
                         "R2D2"
                         "BB-8"]}
   :ships {
           :rebel-alliance  ["Millenium Falcon"
                             "X-wing fighter"]
           :imperial-empire ["Death Star"
                             "Intergalactic Cruiser"
                             "Star Destroyer"
                             "TIE Fighter"
                             "Lambda-class Shuttle"]}})


(get starwars-collection :characters)
~~~


The key we use to get values from a map is at the top level, ie. it is not nested in another map.  If we want to get a nested value we can use a variation of the `get` function called `get-in`.  The `get-in` function takes the map and a vector of keys.

**Try calling each of the functions at the end of this code snippet**

~~~klipse
(def starwars-collection
  {:characters {
                :jedi   ["Luke Skywalker"
                         "Obiwan Kenobi"
                         "Quigon Gin"
                         "Rey"]
                :rebels ["Admiral Gial Ackbar"]
                :sith   ["Darth Vader"
                         "Darth Sideous"]
                :droids ["C-3P0"
                         "R2-D2"
                         "BB-8"]}
   :ships {
           :rebel-alliance  ["Millenium Falcon"
                             "X-wing fighter"]
           :imperial-empire ["Death Star"
                             "Intergalactic Cruiser"
                             "Star Destroyer"
                             "TIE Fighter"
                             "Lambda-class Shuttle"]}})


(get-in starwars-collection [:characters :jedi])

;; (get-in starwars-collection [:ships :rebel-alliance])
~~~

In these most recent examples, the keys used in the map have been defined using the Clojure `keyword` type.  A keyword is most commonly used to find values in a collection, especially maps.

You can also use a keyword as a function, instead of the `get` function.  You can also call a map as if it was a function by using a key as an argument to calling the map as a function.

**Try calling each of the functions at the end of this code snippet**

~~~klipse
(def starwars-collection
  {:characters {
                :jedi   ["Luke Skywalker"
                         "Obiwan Kenobi"
                         "Quigon Gin"
                         "Rey"]
                :sith   ["Darth Vader"
                         "Darth Sideous"]
                :droids ["C3P0"
                         "R2D2"
                         "BB-8"]}
   :ships {
           :rebel-alliance  ["Millenium Falcon"
                             "X-wing fighter"]
           :imperial-empire ["Death Star"
                             "Intergalactic Cruiser"
                             "Star Destroyer"
                             "TIE Fighter"
                             "Lambda-class Shuttle"]}})


; (starwars-collection :characters)
;; (:characters starwars-collection)

;; (:sith (starwars-collection :characters))
;; ((starwars-collection :characters) :sith)
~~~

If you dont get the use of maps and keywords like this, dont worry.  Just try to see that this is a short-hand version of the `(get map keyword)` function call.
