---
layout: curriculum
title: A Piece Of Pie
permalink: /docs/curriculum/a-piece-of-pie
level: easy
author: jr0cket
---


Clojure is able to use fractions as numbers, you may think this is nothing specially, but most other languages do not support this.

Being able to keep a number as a fraction is especially useful when calculating that number would result in a decimal number.  Decimal numbers have a precision, the number of digits after the decimal point.


You will be introduced to the _Ratio_ type and the following functions for the first time:

* `type`, `class`


<hr />


## A quick look at types

Everything you create in Clojure, from maps, lists & vectors through to names and functions have a type.  Its just in Clojure you rarely need to specify a type or concern yourself with the type of something.

The most likely exposure to types you will experience is if you use a value as a function call (remember the first thing in a list is a function call).  For example if you evaluate `(1 2 3 4)` then Clojure will create an error saying that `1` is not an `IFn`.  An `IFn` is the type of a Clojure function.

You can see the type of something by using the function `type`.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(type '(1 2 3 4))
(type [ 1 2 3 4])
(type {:a 1 :b 2})
(type 1)
(type "I am a string")
(type :i-am-a-keyword)
(type def)
(type defn)
</code></pre>



Sometimes you need to change a type when using other languages in Clojure, for example if you are calling methods in Java.


## Almost Pie

If you divide 22 by 7 you get a rough approximation for the value of PI, a mathematical value used to create circles and curves.


<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(/ 22 7)
</code></pre>


## Changing Types - Coercion

If one of the numbers in your calculation is a decimal number then the result would be a decimal number with the same precision, rather than a ratio (fraction). 


**Divide numbers where one number is a decimal**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
()
</code></pre>


https://clojuredocs.org/clojure.core/range

Most functions naturally “want” to be one or the other. For example, the range function, which returns a sequence of (typically consecutive) integers, is lazy: it doesn’t need to calculate the entire sequence when it’s first called, so it doesn’t. It returns a lazy sequence, which is essentially the first item and a promise to compute the next one whenever it’s needed



## Dont blow up 

Clojure features lazy sequences, which are especially useful if a given sequence is too big to fit into memory.

 some functions “want” to be eager. For example, reverse has to go all the way to the end of the sequence in order to return the first item, so it may as well return the whole reversed sequence at once—there’s no benefit here in returning a lazy sequence. Also, although vectors are considered sequences, there is no such thing as a lazy vector, so any function returning a vector (like vec, mapv, or filterv) is de facto eager.
 
 One very good reason to use lazy sequences is that, if you use them “correctly” (a qualification we’ll explore below), they allow you to process “large” sequences that cannot fit into memory. In fact, you can even process infinite sequences!
 
 




Clojure function to lazily reduce a large sequence

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(defn sidelong-reduce
  "Do a lazy reduce, returning the original (lazy) sequence, 
  and passing the final accumulator value to `store-result!` 
  when the sequence is fully realized."
  [seq f accum store-result!]
  (lazy-seq
    (if (empty? seq)
      (do (store-result! accum) nil)
      (let [[fst & rst] seq]
        (cons fst
              (sidelong-reduce rst f (f accum fst) store-result!))))))
</code></pre>



## Eager vs Lazy

functions returning sequences can be classified by whether they return a lazy sequence

functions returning a lazy sequence are called lazy 
function simply returning a sequence are called eager.

Eager functions consume the entire sequence without delay, as programmers coming from non-functional languages often expect. Lazy functions, on the other hand, return a lazy sequence, whose items are not calculated (or “realized”) until they are needed.


Consider filter, which returns a sequence of only the items in the input sequence that pass a given predicate. It doesn’t need to do the full scan up-front. It can simply find the first match (if any), and return a promise to find the next match whenever it’s needed—which is exactly what it does. It’s lazy.





## Pitfalls of large lazy sequences

What do I mean when I talk about using a large lazy sequence “correctly”? You have to be careful that you don’t accidentally force it to all be in memory. For example, simply calling reverse will pull the entire sequence into memory before returning anything, because it has to traverse the entire sequence to get the first item of the returned sequence. Worse yet, the items pulled into memory cannot be garbage collected because they might be needed later. If your sequence is “large”, using the built-in reverse function will break your program; you must instead do something fancy, like a divide-and-conquer algorithm to only reverse a section at a time.

The term Clojurists use to describe this problem is “retaining the head” of the sequence. As an example of head-retaining code, consider this snippet:

(def a (range))
(def b (count a))

If you try running that, it will eventually grind your JVM to a halt because you'll run out of memory. It's trying to exhaust an infinite sequence while retaining a reference (a) to the head of the sequence. The a reference prevents the garbage collector from reclaiming any items once you pass by them. In contrast, consider this code:

(def b (count (range)))

If you try running that, it will never finish (because the sequence is infinite), but it will not run out of memory because the garbage collector is reclaiming items as fast as they are being counted.

So, in summary: don't retain the head.
Motivation for sidelong-reduce

…Except sometimes you really want to retain the head. For example, let's say you have a large sequence of numbers, and you want to both count and sum them. Remember, if you do these operations in succession, you'll be retaining the head, because after the first operation you've fully realized the sequence but still need to keep the head around for the second operation. That's why the following naive solution will throw an OutOfMemoryError:

(defn naive-count-and-sum
  [nums]
  (vector
    (count nums)
    (reduce + 0 nums)))

What are your options? You could rig up some complicated parallel processing jiggery and hope that the two reductions don't get too out of sync. Or you could mash the two reductions together into a single reduction, but doing so entangles the code together in a way that you'd like to avoid in your quest for simplicity and separated concerns. What to do? (Note: I haven't yet understood reducers; if they would solve this problem without entangling the concerns, do let me know!)

There, at long last, is the motivation for the sidelong-reduce function above. With sidelong-reduce, you only perform the reduction as the sequence is realized by some external process. This allows you to wrap a lazy sequence in a sidelong reduction and get the exact same lazy sequence out again, with the result of the reduction published to the given side channel when it's ready. Thus, you can compose an arbitrary number of reductions together (although you still must be careful not to accidentally retain the head).
Example: composing lazy reductions

For example, to both count and sum a large sequence called nums, you can do this:

(defn sidelong-count
  [nums result-atom]
  (letfn [(step [accum item]
            (inc accum))]
    (sidelong-reduce nums step 0 #(reset! result-atom %))))

(defn sidelong-sum
  [nums result-atom]
  (sidelong-reduce nums + 0 #(reset! result-atom %)))

(defn sidelong-count-and-sum
  [nums]
  (let [count-atom (atom nil)
        sum-atom (atom nil)]
    (-> nums
      (sidelong-count count-atom)
      (sidelong-sum sum-atom)
      dorun)
    [@count-atom @sum-atom]))

I admit, using sidelong-reduce is a little more complicated than just using reduce. I think this is the price to pay for having an approach that uses a side channel for results, which I think is necessary given the nature of the problem. However, if you find a more elegant solution, do tell! We might even feature your solution (crediting you, of course) in a followup post.

Note that the dorun is necessary to force the realization of the entire sequence, which is a requirement for sidelong-reduce to ever actually publish a result. (Don't use doall, which intentionally retains the head of the sequence.) In many real-world cases, such as writing a large sequence to disk, you will have some other "driver" forcing the realization of the sequence and won't need to use dorun.
Try it out

If you're curious, try it yourself. Try starting a Clojure REPL, pasting in the sidelong-reduce defn and the above defns, and call it:

(sidelong-count-and-sum (range 100000000))  ;; 100M items
[100000000 4999999950000000]

I did this in a Clojure REPL process with 512 MB of available memory.1 The sidelong version returned the correct answer in about a minute. The naive, head-retaining version threw an OutOfMemoryError.

1 Assuming you've using Leiningen before, you should be able to use this or a similar incantation to start a limited-memory Clojure REPL:

java -Xmx512m -jar \
  ~/.m2/repository/org/clojure/clojure/1.6.0/clojure-1.6.0.jar

