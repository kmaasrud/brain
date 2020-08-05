+++
title = "Clojure quote"
+++

A quote (`'`) in [Clojure]({{< ref "Clojure.md" >}}) means the expression is not evaluated
    - ```clojure
user> (quote (println "foo"))
(println "foo")```
    - Used to make literal lists, for example
        - ```'(1 2 3)``` 
    - Or in [Clojure namespaces]({{< ref "Clojure namespaces.md" >}})
        - ```clojure
(require 'clojure.string)```
