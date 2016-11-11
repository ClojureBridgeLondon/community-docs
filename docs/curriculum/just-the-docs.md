---
layout: curriculum
title: Just The Docs
permalink: /docs/curriculum/just-the-docs
level: easy
author: jr0cket
---



You will be introduced to the following functions for the first time:

* `doc` - show the documentation for a function, eg `(doc map)`
* `source` - show the source code for a function, eg `(source if)`

<hr />

## Clojure.org & ClojureDocs.org

[Clojure.org](https://clojure.org) has a very detailed [Reference](http://clojure.org/reference/reader) section, explaining the various aspects of Clojure.

[ClojureDocs.org](http://clojuredocs.org/) provides a very fast search through the documentation for functions.


## Grimore

The Clojure Grimoire provides a cheetsheet and searchable documentation.  Grimoire also an API, so can be called from editors and other clients.

<a href="https://www.conj.io/"><img src="{{ site.baseurl }}/img/clojure-grimoire.png" width="600"></a>

## In your editor 

Your editor should have features that will show you the documentation and source code of functions.  As soon as you define your own functions, those should be available too.

## In the repl

If you using the REPL from the command line and are in the `user` namespace, then you can simple call `(doc ,,,)` and `(source ,,,)`.

However, if you are in a different namespace or are using the REPL of your editor, you may need to provide the fully qualifier names for these functions:

* `(clojure.repl/doc ,,,)`
* `(clojure.repl/source ,,,)`
