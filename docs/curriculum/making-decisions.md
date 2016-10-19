---
layout: curriculum
title: Making Decisions 
permalink: /docs/curriculum/making-decisions/
level: easy
author: jr0cket
---

Making decisions is an important part of writing programs


## Am I sleepy

We are going to start with the assumption that you are sleepy, it is a Saturday morning after all.

To tell Clojure we are sleepy, we create a _name_ called sleepy and give it a _value_ of `true`.  This name is given a value using the function `def`.

We then test to see if we are sleepy using the `if` function.  If we are sleepy, then the code tells us to have a cup of coffee or tea.

~~~klipse
(def sleepy true)

(if sleepy
  (str "Drink some coffee or a nice cup of tea")
  (str "You are awake, lets code..."))
~~~

In the above code, change the value of the name `sleepy` to the value `false`.  What does the code tell us to do...



## Other decision making functions 


when
cond





## Filtering information based on decisions or conditions 

Decisions are commonly made when processing information

odd?
even?

~~~klipse
(for [x (range 10) :when (odd? x)] x)
~~~

In the above code, try changing the function `odd?` to the function `even?`.

> Using a ? character at the end of a functions name is a convention used in Clojure.  Functions named in this way should return a true or false answer.  Functions named this way are called a [predicate](https://en.wikipedia.org/wiki/Predicate_(mathematical_logic)).



## A combination lock 

You have just bought a new safe too keep all the richest you will gain from becoming a Clojure developer (hopefully).  The safe has a 3 combination lock to protect your new found wealth.

Lets consider how we would create such a combination lock in Clojure.

- The combination is managed by three tumbler wheels
- Each tumbler wheel has the same range of numbers on then, 0 to 9

Each tumbler wheel could have all the numbers it contains within a _Collection_ in Clojure.  The simplest approach would be to put the numbers 0 to 9 into a Vector (an array-like collection).

~~~klipse
[0 1 2 3 4 5 6 7 8 9]
~~~

As the numbers on the tumbler wheel are just a range between 0 and 9, then rather than type out all the numbers we can use the `range` function to generate all the numbers for us.  

When we give the range function one argument, it will create all the whole numbers from 0 to the number before that of the argument.  In the following example, we give `range` the argument of 10 and we receive the numbers from 0 to 9. 

~~~klipse
(range 10)
~~~

You can also give `range` two arguments, such as '(range 5 15)'.

> Be careful not to call the `range` function by itself, or it will try and generate an infinite range of numbers (until your computer memory is all used up).


### Create all the Combinations

Complete the following code (replacing the ,,,) to generate all the possible combinations of the lock

~~~klipse
(for [tumbler-1 (range 10)
      ,,,     ,,,
      ,,,     ,,,]
 [tumbler-1 ,,,   ,,,])
~~~

Instead of showing all the possible combinations, count all the combinations and return the total number of combinations

~~~klipse
;; now count the possible combinations
(count 
       
       
         )
~~~

To make our lock harder to break into, we should only allow the combinations where each tumbler wheel has a different number.  So you cannot have combinations like 1-1-1, 1-2-2, 1-2-1, etc.

How many combinations does that give us? 

~~~klipse
(count (for [,,,     ,,,
             ,,,     ,,,
             ,,,     ,,,
             :when (or (= tumbler-1 tumbler-2)
                       ,,,
                       ,,,)]
         [tumbler-1 ,,,   ,,,]))
~~~

