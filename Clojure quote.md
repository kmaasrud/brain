A quote (`'`) in [[Clojure]] means the expression is not evaluated
    - ```clojure
user> (quote (println "foo"))
(println "foo")```
    - Used to make literal lists, for example
        - ```'(1 2 3)``` 
    - Or in [[Clojure namespaces]]
        - ```clojure
(require 'clojure.string)```
