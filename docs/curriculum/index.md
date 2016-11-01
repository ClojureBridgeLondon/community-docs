---
layout: curriculum
title: Hello World 
permalink: /docs/curriculum/
level: easy
author: jr0cket
---

Welcome to the curriculum for ClojureBridge.

This curriculum is suitable for those new to programming and you should work through it at your own pace.

Existing developers may go through this content more quickly, especially in the sections marked _Easy_.  Or if you have the basics of the Clojure syntax then simply jump straight to the challenges.


# Hello Clojure World

Here is a very simple bit of Clojure to get you started.  You can change the code and as you do so the result of the code changes underneath...

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(str "Hello" " " "World")
</code></pre>

You do not have to use a Clojure aware editor to complete this curriculum, however you may find it useful to copy code into an editor for further reference or experimentation.

The ability to run you code like this is thanks to a Clojurescript project called [Klipse](https://github.com/viebel/klipse).  Clojurescript is the Clojure language turned into Javascript and run in the browser to create interactive apps and webpages such as this one.


# Why Clojure?

There are [many great features in Clojure](http://practicalli.github.io/clojure/overview/) that you will discover, some of which were presented during the ClojureBridge install party.

Clojure is a general purpose programming language and can be used to create most of the applications you could write in other languages.

[Many well known companies](http://practicalli.github.io/clojure/overview/who-uses-clojure.html) are using Clojure and companies in locations such as London and San Francisco have a great many opportunities to work with the language.


# Contributing to Curriculum

## Adding a new section 

Create a new markdown file under docs/curriculum and ensure it has the curriculum layout (or copy an existing markdown file).

To include a new section in the navigation, add the new section to the `_data/curriculum.yml` file.
