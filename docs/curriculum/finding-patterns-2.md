---
layout: curriculum
title: Making Decisions
permalink: /docs/curriculum/finding-patterns/
level: intermediate
author: jr0cket
---


This section introduces functions 

* `slurp`
* `re-seq`
* `frequencies`, `sort-by`, `reverse`
* `remove`
* `clojure.string/split`


## Retrieve a message from your spy

Slurp in some data from the interweb.... a file on the clojurebridgelondon repo?


## Converting a document into individual strings 

~~~klipse
(re-seq "regular expression" "long string of worlds, etc")
~~~


## Decoding the message 


## Frequency 

Find out how often something appears in a collection 





Exercise - looking for a door code in a death star manual
- break up the manual into words
- find where the word code is and get the next value


Space parens challenge
- retrieve a message from your spy
- decode the message - the most common word in a message is always xxx, which can then be used to discover the code used to encrypt the message




## Challenge this section supports 



;; Book: The importance of being Earnest, Oscar Wilde
;; Source: Project Guttenburg (UTF-8 format)
(def book (slurp "http://www.gutenberg.org/cache/epub/844/pg844.txt"))

book

(def common-english-words
  (-> (slurp "http://www.textfixer.com/resources/common-english-words.txt")
      (clojure.string/split #",")
      set))

(reverse
  (sort-by val
           (frequencies
             (remove common-english-words
                     (map #(clojure.string/lower-case %)
                          (re-seq #"[a-zA-Z0-9|']+" book))))))



;; using a function to pull in any book
#_(defn get-book [book-url]
  (slurp book-url))


(defn -main [book-url]
  (->> #_(get-book book-url)
       book
       (re-seq #"[a-zA-Z0-9|']+")
       (map #(clojure.string/lower-case %))
       (remove common-english-words)
       frequencies
       (sort-by val)
       reverse))

;; Call the program

(-main "http://clearwhitelight.org/hitch/hhgttg.txt")
