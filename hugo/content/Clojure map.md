+++
title = "Clojure map"
+++

Maps are [Clojure]({{< ref "Clojure.md" >}})'s type of [Associative array]({{< ref "Associative array.md" >}})
- A map is created in [Clojure]({{< ref "Clojure.md" >}}) using the following syntax:
    - ```clojure
(def my-map {:value-1 1
             :value-2 2
             :value-3 3})```
        - The keywords don't need to be a [keyword type]({{< ref "Clojure keyword.md" >}}), but this is convention.
        - There's also no need to have the entries on separate lines, but this increases readability.
- Adding values to an existing map is done via the [assoc]({{< ref "Clojure assoc.md" >}}) function
    - ```clojure
user=> (assoc my-map :value-4 4)
{:value-1 1, :value-2 2, :value-3 3, :value-4 4}```
- Removing values from an existing map is done via the [dissoc]({{< ref "Clojure dissoc.md" >}}) function
    - ```clojure
user=> (dissoc my-map :value-2)
{:value-1 1, :value-3 3}```
- Looking up a key is done two ways:
    - Either via the [get]({{< ref "Clojure get.md" >}}) function:
        - ```clojure
user=> (get my-map :value-1)
1```
    - or via invoking the map itself:
        - ```clojure
user=> (my-map :value-1)
1```
        - This is sensitive to [null values]({{< ref "Null.md" >}})
            - Example:
                - ```clojure
user=> (def bad-lookup-map nil)
#'user/bad-lookup-map

user=> (bad-lookup-map :foo)
Execution error (NullPointerException) at user/eval154 (REPL:1).
null```
    - You can fallback on a default if necessary
        - ```clojure
user=> (get my-map :value-5 0)
0

user=> (my-map :value-0 "Yo")
"Yo"```
- Sources:
    - [clojure.org](https://clojure.org/guides/learn/hashed_colls#_maps)
