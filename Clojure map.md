Maps are [[Clojure]]'s type of [[Associative array]]
- A map is created in [[Clojure]] using the following syntax:
    - ```clojure
(def my-map {:value-1 1
             :value-2 2
             :value-3 3})```
        - The keywords don't need to be a [[Clojure keyword|keyword type]], but this is convention.
        - There's also no need to have the entries on separate lines, but this increases readability.
- Adding values to an existing map is done via the [[Clojure assoc|assoc]] function
    - ```clojure
user=> (assoc my-map :value-4 4)
{:value-1 1, :value-2 2, :value-3 3, :value-4 4}```
- Removing values from an existing map is done via the [[Clojure dissoc|dissoc]] function
    - ```clojure
user=> (dissoc my-map :value-2)
{:value-1 1, :value-3 3}```
- Looking up a key is done two ways:
    - Either via the [[Clojure get|get]] function:
        - ```clojure
user=> (get my-map :value-1)
1```
    - or via invoking the map itself:
        - ```clojure
user=> (my-map :value-1)
1```
        - This is sensitive to [[Null|null values]]
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
