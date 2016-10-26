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

We can write a sentence about ourselves as a _string_.  A string is a collection of characters and is always between double quotes, for example `"I am a string"`.

Lets look at the simplest possible way you could write some information about yourself

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
"John Stevenson, age 21, height 6ft4, blue eyes, dark and brooding"
</code></pre>


## Naming Things with `def`

The function `def` can be used to give a name to something, or more specifically we are defining a name for a value.  For example, you can give a name to a string or number or most other things in Clojure.

Lets define a name that contains a string of our name.  Try defining names for other values too.

~~~klipse
(def my-name "John Stevenson")

;; (def my-preferred-age 25)
;; (def favourite-language "Clojure")
;; (def my-group ["Tina" "Belinda" "Harmony"])
~~~

To get the value of a name you can simply use the name in your code

~~~klipse
my-name

;; my-age
~~~

Its much more common to use the name with a function though

~~~klipse
(str my-name " is enjoying coding in Clojure")
~~~

Giving a name to something allows you to easily use that thing elsewhere in your code.  The name can be used instead of typing out the value in multiple places.  If you want to change the value used throughout your code, then you only need to change your code in one place.


## Grouping things together in a Collection

So going back to defining ourselves, how can we can give a name to all our details ?

We could also use a Clojure collection to hold lots of values about ourselves.

Using the square brackets,`[ ]` represents a _vector_ in Clojure.  A _vector_ is a very flexible box you can put any kind of _values_ in (strings, numbers, characters, function calls, names, true, false, keywords).

There is no limit to the number or types of values you can put into a vector (although an infinite number of values could prove tricky all at once)

> Note: a vector is often used in Clojure as its such a flexible and easy to use collection.

~~~klipse
["John" "Stevenson" "37" "Clojure" "London" "North Yorkshire" 12]
~~~

Once of the disadvantages of a _vector_ is ambiguity.  Just by looking at the vector its not always obvious as to what each value represents.

For example, we can infer that "John" and "Stevenson" are probably the persons first and last names.  However, is this person's age 37 or is it 12.  If that person is aged 37 then what does the 12 represent.  Is it they years they have lived in London, is it the age they left North Yorkshire or is it simply their shoe size


~~~klipse
(def my-details ["John" "Stevenson" "37" "Clojure" "London" "North Yorkshire" 12])
~~~

As we already defined `my-name` as a name that points to my full name, we can use `my-name` as part of the collection for `my-details`

~~~klipse
(def my-details [my-name "37" "Clojure" "London" "North Yorkshire" 12])
~~~


> Hint: Any names we define in this page will be available to any sections of code after the definition of that name.



### Examples of Collections

A collection is a common programming concept that simply is a container that holds other values.

Examples of collections in your life could be your CD collection, your Spotify lists of music, or your wish list of things you want to buy on Amazon.

A collection is often made up of similar things or things that are related to each other in some way.  In some languages collections contain the same types of things, whereas Clojure collections can contain anything, just like cardboard boxes packed in a hurry on the day you move house.

Collections in Clojure can contain any valid Clojure value or expression ("string", 99, 3/4, (str "function call")).



## Getting information from collections

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


## Giving meaning to data with maps

Another common collection in Clojure is a _map_.  A map is a collection that contains pairs of keys and values.  The keys allow you to look up the values in a map.

~~~klipse
{"key" "value}

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


### Exercise

Define information about yourself using a _map_, using Clojure _keywords_ as the keys of the map and strings or numbers for the values.

Remember that a valid map must have a key and a value as a pair.  You can have multiple key-value pairs in a map.

~~~klipse
{:firstname "John" ,,, ,,,}
~~~



## Describing more complex things

We have represented ourselves as a fairly simple structure, just as a collection of values, mainly strings and numbers.

We can also include collections as elements in a collection.

~~~klipse
["my-friends" ["Kerry" "Chris" "Abby"]]

;; {:types-of-pet ["cat" "dog" "tropical fish" "rabbit"] }

;; {:bicycle ["wheels" "frame" "handlbars"]}
~~~

Imagine our meal is made up of a starter, main course and dessert.  How could we represent that?

~~~klipse
{}
~~~

Now we want to define what makes up each part of the meal.  So how do we show what we have for the starter, main course and dessert?

~~~klipse
{}
~~~

Once you have finished these exercises, take a look at the [suggested answers](https://gist.github.com/f0bae2a5bd4e92a3db4d6e51246c3dfe)


## Finding information in maps

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
(get starwars-collection :characters)
~~~


The key we use to get values from a map is at the top level, ie. it is not nested in another map.  If we want to get a nested value we can use a variation of the `get` function called `get-in`.  The `get-in` function takes the map and a vector of keys.

**Evaluate each of the functions by un-commenting them in turn**

~~~klipse
(get-in starwars-collection [:characters :jedi])

;; (get-in starwars-collection [:ships :rebel-alliance])
~~~


## A little short-cut with keywords

In these most recent examples, the keys used in the map have been defined using the Clojure `keyword` type.  A keyword is most commonly used to find values in a collection, especially maps.

You can also use a keyword as a function, instead of the `get` function.

You can also call a map as if it was a function by using a key as an argument to calling the map as a function.

**Try calling each of the functions at the end of this code snippet**

~~~klipse
; (starwars-collection :characters)
;; (:characters starwars-collection)

;; (:sith (starwars-collection :characters))
;; ((starwars-collection :characters) :sith)
~~~

If you dont get the use of maps and keywords like this, dont worry.  Just try to see that this is a short-hand version of the `(get map keyword)` function call.
