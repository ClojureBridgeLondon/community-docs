---
layout: curriculum
title: Making Decisions
permalink: /docs/curriculum/making-decisions/
level: easy
author: jr0cket
---

Making decisions is an common part of writing code, so in this section we will cover functions in Clojure that help us take decisions.

You will be introduced to the following functions for the first time:

* `if` - make a decision based on some true or false condition
* `odd?`, `even?` - test if a value is odd or even and returns true or false (predicates)
* `true`, `false` - Boolean values that represent true and false

<hr />

## Is it true or false - the `if` function

The `if` function we do something based on whether some condition is either true or false.  If the condition is true, then do the first thing.  If the condition is false, then do the second thing.

```clojure
(if condition
  "true - then evaluate and return me"
  "false - then evaluate and return me")
```

## Conditions

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

A condition can be a simple value, like `true` or `false`, or it can be the result of a function call that gives either a `true` or `false` value.

**Guess which of the following conditions return a true or false value**

```clojure
(= 1 1)
(= "Hello" "Clojure")
(< 3 4)
(> 3 4)
(odd? 3)
(even? 7)
```

To check your answers, copy / paste a line of the code above into the code box below to see if you are correct.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">

</code></pre>


## Am I sleepy

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

We are going to start with the assumption that you are sleepy, it is a Saturday morning after all.  If you are sleepy, then you could get a nice cup of tea or coffee.  If you are wide awake then you can start coding.

**Assign a name to the true or false value**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def sleepy )
</code></pre>


**Write an if statement to decide what to do if you are sleepy**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(if sleepy )
</code></pre>

Change the value of `sleepy` to see what does the code tell us to do...

See the [suggested example](https://gist.github.com/jr0cket/46666ac40070da1e988f980858354554)
