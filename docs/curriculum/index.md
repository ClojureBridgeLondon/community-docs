---
layout: curriculum
title: Hello World 
permalink: /docs/curriculum/
level: easy
author: jr0cket
---

Welcome to the curriculum for ClojureBridge.

This curriculum is suitable for those new to programming and it will teach you the basics of programming in Clojure.

Existing developers may wish to go through this content at a quicker pace, especially the sections marked _Easy_.  Or if you have the basics of the Clojure syntax then you could simply jump straight to the challenges.


# Hello Clojure World

Here is a very simple bit of Clojure to get you started.  You can change the code in the top row and as you do so the result of the code changes underneath.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(str "Hello" " " "World")
</code></pre>

We will explore many of the functions like `str` in Clojure which allow us to create a wide range of behaviour in our programs.

Functions are the first thing inside a list, where is list is denoted by `()`.  Everything after the function name is information (arguments) we pass to the function that can change the result.

We will cover the use of functions in much more detail, including defining your own, as we go through the curriculum.

## The Clojure REPL

The code section above is an example of a Clojure REPL.  A REPL is a way to run Clojure code, either as full program or just specific lines of code.

You can write any Clojure code in the REPL get instant feedback on what that code does.

![Clojure REPL in action (Klipse)](https://raw.githubusercontent.com/viebel/klipse/master/images/clojure-snippet.gif)

You can complete this curriculum using the REPL in these web pages, however you may find it useful to copy code into an editor for further reference or experimentation.

> The ability to run you code like this is thanks to a Clojurescript project called [Klipse](https://github.com/viebel/klipse).  Clojurescript is the Clojure language turned into Javascript and run in the browser to create interactive apps and webpages such as this one.


# Why Clojure?

There are [many great features in Clojure](http://practicalli.github.io/clojure/overview/) that you will discover, some of which were presented during the ClojureBridge install party.

Clojure is a general purpose programming language and can be used to create most of the applications you could write in other languages.

[Many well known companies](http://practicalli.github.io/clojure/overview/who-uses-clojure.html) are using Clojure and companies in locations such as London and San Francisco have a great many opportunities to work with the language.


# Contributing to Curriculum

## Adding a new section 

Create a new markdown file under docs/curriculum and ensure it has the curriculum layout (or copy an existing markdown file).

To include a new section in the navigation, add the new section to the `_data/curriculum.yml` file.
