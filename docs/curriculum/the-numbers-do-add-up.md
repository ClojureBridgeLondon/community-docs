---
layout: curriculum
title: The Numbers Do Add Up
permalink: /docs/curriculum/the-numbers-do-add-up
level: easy
author: jr0cket
---

In this section you will learn some of the Clojure functions for basic mathematics along with how to define your own simple functions. 

We can change things in many ways in Clojure, however most of the time it looks like we change things, we are merely making new things from the old ones.  For example, when we add two numbers we dont actually change either number, instead we create a third number that is the result.

We will also introduce the following functions for the first time:

| `+`, `-`, `*`, `/`, `<`, `>` | basic arithmetic functions                       |

<hr />


## Simple addition

You can use existing functions by putting the name of the function as the first thing in a list, `()`.

Lets do some simple math

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(+ 1 2 3)
</code></pre>

> Note: You can call a mathematical function with one or more arguments

**Try out some simple maths** 

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(+ )

;; (- )
;; (* )
;; (/ )
;; (< )
;; (> )
</code></pre>


## Prefix notation

You have seen lots of examples of prefix notation in Clojure so far.  In fact all of Clojure uses prefix notation.

Prefix notation means that the function comes first, followed by all the arguments.  The function is a pre-cursor to the data the function is going to work on.


> FIXME: add some more mathematical examples
