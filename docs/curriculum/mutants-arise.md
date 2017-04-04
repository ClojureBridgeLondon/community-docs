---
layout: curriculum
title: Mutants Arise 
permalink: /docs/curriculum/mutants-arise
level: easy
author: jr0cket
---

In this section you will apply changes to values, how to define your own simple functions.

We will also introduce the following functions for the first time:

| `atom`       | create an anonymous function, one without a name |
| `deref`, `@` | assign a name to a function                      |

<hr />

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def mutants (atom []))

(defn add-mutant [mutant]
  (swap! mutants conj mutant))

(add-mutant "Black Widow")
</code></pre>
