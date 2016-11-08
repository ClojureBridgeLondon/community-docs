---
layout: curriculum
title: Who Are We
permalink: /docs/curriculum/who-are-we
level: easy
author: jr0cket
---

Lets define some information about the group we are part of at ClojureBridge.

In the previous section we defined ourselves as a collection, something like the following.

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-details ["John Stevenson" "37" "Clojure" "London" "North Yorkshire" 12])

my-details
</code></pre>

We also defined simpler definitions to hold just our name

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-name "John Stevenson")

my-name
</code></pre>

> Hint: We can use both of these definitions in the next exercises.

## So who are we?

We can use a Clojure collection to hold lots of values about the group we are in.

**Define the group you are in and give that group a name**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-group [])
</code></pre>

Here is a [suggested example](https://gist.github.com/6df8022aee312da586ca5561c3bc9baa) with a fictitious group

### Nesting Collections

As we already defined `my-name` as a name that points to my full name, we can use `my-name` as part of the collection for `my-group`

**Try Nesting Collections so you can include even more information**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-group [])
</code></pre>

Here is a [suggested example](https://gist.github.com/ad985c7403d6ec5f3fc8e86a55bf8031) of a group with a nested collection.

> Remember: Any names we define in this page will be available to any sections of code after the definition of that name.

**Try defining more details about your group using vectors within vectors**

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-group
  [

  ])
</code></pre>

Here is a [suggested example](https://gist.github.com/0182e36ec1459c9e4f90f03d0606e275) using the `my-details` name defined at the start of this section.

The name `my-details` is already associated with a vector collection containing my details, so its not necessary to put `my-details` in a vector as we can just use the name.
