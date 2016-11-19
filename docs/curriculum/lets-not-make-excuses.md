---
layout: curriculum
title: Lets Not Make Excuses
permalink: /docs/curriculum/lets-not-make-excuses
level: easy
author: jr0cket
---

We can Making decisions is an common part of writing code, so in this section we will cover functions in Clojure that help us take decisions.

You will be introduced to the following functions for the first time:

* `let` - assign a name to a value (a value being a number, string, collection or function)
* `cond`, `case` - make a decision based on some condition

<hr />

## Local names with `let`

So far we have given names to values using the `def` function.  This makes the name available throughout our code (and the page in this curriculum).

If we only need to use a name in the same few lines of code, we can use the `let` function instead.

In our previous making decisions examples using the `if` function, we could have used the `let` function instead

```
(let [sleepy true]
  (if sleepy
    "Drink some coffee or a nice cup of tea"
    "You are awake, lets code...")
```
> A let function gives a name to a value, just like the def function.  However, you can only use the name inside of the parenthesis around the let function.

## Making decisions with `cond`

So far we have made a "true or false" decision using the `if statement`.  With the `cond` function you can make a decision based on the value of a condition.  Which ever condition matches, its associated expression will be evaluated and returned.

The `cond` function returns the answer based on the first matching condition it finds.  Each condition will return either true or false.  The first condition to return true will return its associated answer.

We need to have some value to check in the `cond` function, so either a name defined by `def` or `let` can be used.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(let [sleepy "maybe"]
  (cond
    (= sleepy "no")    "Lets code some more..."
    (= sleepy "maybe") "Take a few deep breaths"
    (= sleepy "yawn")  "Time for a brisk walk"
    (= sleepy "zzzz")  "Drink some coffee or a nice cup of tea"
    :else "You must be asleep"))
</code></pre>


## Homework Excuse Generator

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

**Create a simple excuses generator that will return a suitable excuse based on the reason specified**

Fill in the following code, especially where there are `,,,` characters.



<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(let [reason ,,,]
  (cond
    (= reason ,,, )      "I see green elephant-shaped spots"
    ,,,
    ))
</code></pre>


Suggested approach
* create a local _name_ using the `let` function for the value of reason
* Use `cond` to match the reason with the different excuses you want to generate

Once you have tried to solve this exercise, take a look at the [suggested example](https://gist.github.com/09296ae4ff98d48f4a6a729fc479219f)

> Note: This example could have also used the `def` function to assign the name `reason` to the value of the excuse, eg. "sick".  The main difference is that the name assignment only works within the `let` function, meaning that once the closing bracket `)` of the `let` function is reached then the name `reason` can no longer be used.



## Bonjour Clojure with `case`

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

The `case` function is slightly simpler version of the `cond` funciton, simply returning an expression based on which value matches the case.

In our example, we have joined an international company and we want our code to speak a few different languages.  Lets set the language we want to greet people in and return the appropriate message.

**Add different greetings in other languages**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->

<pre><code class="language-klipse" data-eval-context="expr">
(let [greeting :fr]
  (case greeting
    :fr "bonjour monde clojure"
    ,,,
     ))
</code></pre>

In Italian you would say `"ciao mondo clojure"` or in Spanish you could say `"hola mundo clojure"`.

Once you have tried to solve the challenge, see the [suggested example](https://gist.github.com/e72a6ffc416d3d0a609e4782f3a6b90e).


## Bonus challenge

<img src="{{ site.baseurl }}/img/clojurebridgelondon-mini-challenge.png" class="mini-challenge" />

Now lets also decide if we want to return the message in uppercase.  We will change our code around a little first though.  We will define a name called language to hold the keyword for the language we want to use.  Then we will define the message we want to return, using the `case` function.  Finally we will decide whether to convert the message to uppercase characters.

**Try changing the value of `upper-case?` to `false` and changing the language value**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(let [language :fr
      message (case language
                :fr "bonjour monde clojure"
                ,,, )
      upper-case? true]
  (if upper-case?
    (clojure.string/upper-case message)
    message))
</code></pre>


[suggested example](https://gist.github.com/20f261d70edc3895e5378afff16a7137)
