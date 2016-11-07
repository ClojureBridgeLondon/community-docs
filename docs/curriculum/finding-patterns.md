---
layout: curriculum
title: Finding Patterns
permalink: /docs/curriculum/finding-patterns
level: easy
author: jr0cket
---

Sometimes we just want a specific piece of information or just want to do something to a specific sub-set of the information we have.

You will be introduced to the following functions for the first time:

* `slurp` - get the contents of a file or web page
* `clojure.string/split` - split words based on a character or pattern
* `frequencies`, `remove`, `sort-by`, `reverse` - to organise data
* `re-seq` - create a new sequence by applying a pattern to an existing sequence

<hr>


> A classic tale of needing to update data was the Year 2000 bug.  Back in the 1970's and 80's a lot of computer systems simply used 70 to represent 1970, or 77 to represent 1977.  At the time this saved space.  However, as we approached the year 2000 we would no longer know if 70 referred to 1970 or 2070.  With even earlier dates such at 10, then is would soon be impossible to know if that meant 1910 or 2010.  So a lot of information had to be updated, simply by changing the date rather than the whole record.

# Grabbing information from files & websites

The easiest way to get information from a file in your current project is to use the `slurp` command.

> FIXME: wagamama type image to show some slurping 

Just like eating soup or noodles, you slurp the contents of the bowl into your mouth.

The `slurp` function slurps the contents of a file into a collection.


We have created a file full of the common English words and your challenge is to get the contents of the file and return it as a string


<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(str "Hello" " " "World")
</code></pre>



> FIXME create a similar file to the common English words, but add some duplicates


# split 

split the contents of the file so that you have a collection of individual words



# Are there any duplicate words 



# Ensure the words are unique

There is a collection called a _set_ that can hold any values, but those values must be unique.

If you write a set collection with duplicate values, evaluating that set will cause an error.

If you use a function to create a set, any duplicate values will be dropped, but no error will be returned.

