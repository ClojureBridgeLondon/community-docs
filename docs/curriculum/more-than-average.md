---
layout: curriculum
title: More Than Average
permalink: /docs/curriculum/more-than-average
level: easy
author: jr0cket
---

> FIXME: This section goes quite deep into working with collections, add a section before this that is average and make this one intermediate.  It is meant to be a pre-cursor to split the bill, which is a challenge that uses many of these examples to complete.  I think it probably goes to deep and covers too many functions.

In this section we will introduce fuctions that help you work with collections in Clojure.

* `reduce` - creates a single value from the elements of a collection 
* `map` - creates a new collection from processing one or more collections
* `count` - return the total elements in a collection

We will also cover the use of anonymous functions and the `partial` function, to show how to call functions with multiple arguments if one of those arguments are the elements of a collection.

<hr>

## Find the average

Lets start with a simple example that takes three angles and works out the average angle.  To find the average we will add the angles together and divide by 3

~~~klipse
(defn average-simple
  [angle1 angle2 angle3]
  (/ (+ angle1 angle2 angle3) 3))

(average-simple 30 90 50)
~~~


### Average using data in maps

Lets create another function called `average-maps` that takes a vector of maps, using `[{:angle 30} {:angle 90} {:angle 50}]` as data.

Calculate average value of :angle.

> Hint: You will need to use the functions `get`, `map`, `reduce` and `count`.


In the exercise itself, our values are contained within a collection, in this case a map.  So to solve this exercise, at some point we need to extract our values.

Previously we worked with values in a collection (a map) and used the get function.  We also used the feature of keywords to help us get values from maps.  We can use one of the following to extract values from our collection of angles

~~~klipse
(get {:angle 30} :angle)
~~~

~~~klipse
(:angle {:angle 30})
~~~

When we have several maps in a vector, we need to iterate over each map and extract each of the values.  We can use the map function to extract all the values of each map in the vector however the get function we nomally would use isnt sufficient because the `get` function requires two arguments, the map & the key

Neither of these expressions are correct because they call the get function incorrectly.

~~~klipse
;; These examples fail

;; (map get [{:angle 30} {:angle 90} {:angle 50}] :angle)
;; (map get :angle [{:angle 30} {:angle 90} {:angle 50}])
~~~


To solve this we can use a fuction called partial.  The partial function allows you to call another function, but with a missing argument

;; In a simple example we add 90 to every number in the collection

~~~klipse
(map (partial + 90) [0 30 60 90])
~~~


For the exercise we use partial with the :angle keyword, which is passed each map in turn as a second argument by the map function.

~~~klipse
(map (partial :angle) [{:angle 30} {:angle 90} {:angle 50}])

;; Alternative examples
;; (map #(get % :angle) [{:angle 30} {:angle 90} {:angle 50}] )
;; (map :angle [{:angle 30} {:angle 90} {:angle 50}])
~~~

Now we can get all the values returned in a collection, we need to add them.  If we want to take all the values in a collection and get a single value then you can use the reduce function.
;; Here we reduce these values by adding them together

~~~klipse
(reduce + [30 90 50])
~~~

Lets give a name to our angles data, to make it easy to work with

~~~klipse
(def angles [{:angle 30} {:angle 90} {:angle 50}])
~~~

Now we can check our map expression

~~~klipse
(map (partial :angle) angles)
~~~

We want the total value of all the angles, so we reduce them with the + function into one value

~~~klipse
(reduce + (map (partial :angle) angles))
~~~

Now we need the average, so we divide the total value by the number of angle values.  In this example, the count function returns how many maps are in the vector (there is one angle value per map)

~~~klipse
(/ (reduce + (map (partial :angle) angles)) (count angles))
~~~

Now we can put this all in a function definition, so we can call it multiple times (if needed)

~~~klipse
(defn average [angles]
  (/ (reduce + (map (partial :angle) angles)) (count angles)))
~~~

Now we call the average function with the arguments from the exercise

~~~klipse
(average [{:angle 30} {:angle 90} {:angle 50}])
~~~

As we use the count function to help us find the average, we can call average with any number of maps in our vector

~~~klipse
;; (average [{:angle 30} {:angle 90} {:angle 50} {:angle 60}])

;; (average [{:angle 30} {:angle 90} {:angle 50} {:angle 60} {:angle 80}])
~~~



###  Alternative - anonymous function

Instead of using the partial function, you can use an anonymous function.  In this case we are using the short-hand syntax for an anonymous function.

~~~klipse
;; (map #(get % :angle) angles)

;; (reduce + (map #(get % :angle) angles))

;; (/ (reduce + (map #(get % :angle) angles)) (count angles))
~~~



### Let - local names / bindings

Here we use the let function to bind the name `number-of-angles` to the number of angle maps passed in as the argument.

We can then use `number-of-angles` as the value to divide the total, giving us the average value.  Local bindings are only within the scope of the let expression, so calling number-of-angles after the closing perentesis of the let will cause an error.

~~~klipse
(defn average [angles]
  (let [number-of-angles (count angles)]
    (/ (reduce + (map (partial :angle) angles)) number-of-angles)))

(average [{:angle 30} {:angle 90} {:angle 50}])
~~~
