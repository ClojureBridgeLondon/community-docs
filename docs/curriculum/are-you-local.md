---
layout: curriculum
title: Are You Local
permalink: /docs/curriculum/are-you-local
level: easy
author: jr0cket
---

> FIXME: Should go somewhere after the basics of maps have been introduced

Combine the basics of using vectors with the if & filter functions to see who lives locally and who is originally from some other country.


You will be introduced to the following functions for the first time:

* `contains?` - may drop this
* `filter` - only returns the values that return true from the function used with filter (a predicate)

<hr />

> FIXME: turn the code into a proper page 

<!-- Using expression evaluation fix to make string appear as a value in klipse -->
<pre><code class="language-klipse" data-eval-context="expr">
(def my-team
  [{:firstname "John" :lastname "Stevenson" :hometown "North Yorkshire" :work-location "London"}])

;; ;; (contains? (first my-team) :hometown)

;; ;; (= (get (first my-team) :hometown) "London")


;; (defn are-you-local?
;;   "Takes a map of a team member to see they were born locally or are a welcome traveller to this land"
;;   [team-member]
;;   (if (= (get team-member :hometown) "London")
;;     "Hello Native"
;;     "Welcome traveller"))

;; (map are-you-local? my-team)

;; ;;;;;;;;;;;;;;;;;;;;;;;;

;; (defn born-in-london?
;;   "Takes a map of a team member to see they were born locally or are a welcome traveller to this land"
;;   [team-member]
;;   (if (= (get team-member :hometown) "London")
;;     true
;;     false))

;; (def my-team
;;   [{:firstname "John" :lastname "Stevenson" :hometown "North Yorkshire" :work-location "London"}
;;    {:firstname "Jenn" :lastname "Svennsson" :hometown "London" :work-location "London"}])

;; (filter born-in-london? my-team)

;; ;;;;;;;;;;;;;;;;;;;;;;;;

;; (defn born-locally?
;;   "Takes a map of a team member to see they were born locally or are a welcome traveller to this land"
;;   [team-member]
;;   (if (= (get team-member :hometown) "London")
;;     true
;;     false))

;; (defn work-in-london?
;;   "Takes a map of a team member to see they were born locally or are a welcome traveller to this land"
;;   [team-member]
;;   (if (= (get team-member :work-location) "London")
;;     true
;;     false))

;; (defn are-you-worldly
;;   [team-member]
;;   (let [works-locally (local-to-london? team-member)
;;         born-locally  (born-locally? team-member)]
;;     (if (and works-locally born-locally)
;;       false
;;       true)))

;; (filter are-you-worldly my-team)


;; (map (fn [team-member] (get team-member :hometown)) my-team)

;; (defn hometown
;;   [team-member]
;;   (get team-member :hometown))

;; (map hometown my-team)

</code></pre>
