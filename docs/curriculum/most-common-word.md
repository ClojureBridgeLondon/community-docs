---
layout: curriculum
title: Most Common Word
permalink: /docs/curriculum/most-common-word
level: intermediate
author: jr0cket
---

In this challenge we would like you to find the most used word in a book.  The word should not be part of the common English words (i.e. the, a, I, is).


## Resources 

Copyright free books for use are available via [Project Guttenburg](http://www.gutenberg.org/).  We suggest the book titled "The Importance of Being Earnest" by Oscar Wilde.

http://www.gutenberg.org/cache/epub/844/pg844.txt

A comma separated list of all the common English words is available at:

http://www.textfixer.com/resources/common-english-words.txt


## Suggested approach 

A suggested algorithm to find the most common word is:

* Pull the content of the book into a collection
* Use a regular expression to create a collection of individual words - eg. #"[a-zA-Z0-9|']+"
* Convert all the words to lower case so they match with common words source 
* Remove the common English words used in the book
* Count the occurrences of the remaining words (eg. each word is associated with the number of times it appears in the book)
* Sort the words by the number of the occurrences
* Reverse the collection so the most commonly used word is shown first


<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(str "Delete me and add your code to solve the challenge.  Use a Clojure editor if you prefer")
</code></pre>


<hr />

Once you have solved this challenge, take a look at the suggested answers to the problem.

* [Suggested answer in lisp style](https://gist.github.com/05941171b7514e60102aa4fe026d73b6)
* [Suggested answer using threading macro](https://gist.github.com/4601d4523b4bc3b31cd0cc2afb05a705)

