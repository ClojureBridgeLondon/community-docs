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


<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details ["John" "Stevenson" "37" "Clojure" "London" "North Yorkshire" 12])
</code></pre>


As we already defined `my-name` as a name that points to my full name, we can use `my-name` as part of the collection for `my-details`

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details [my-name "37" "Clojure" "London" "North Yorkshire" 12])
</code></pre>

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


### Exercise

Define information about yourself using a _map_, using Clojure _keywords_ as the keys of the map and strings or numbers for the values.

Remember that a valid map must have a key and a value as a pair.  You can have multiple key-value pairs in a map.

~~~klipse
{:firstname "John" ,,, ,,,}
~~~

> FIXME: Split into another section - Making a meal of it

