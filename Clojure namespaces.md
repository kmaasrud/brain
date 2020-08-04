In [[Clojure]], including an available namespace into a program is done via the `require` function, passing the required namespace in as a [[Clojure quote|quoted]] symbol:
    ```clojure
user=> (require 'clojure.string)
nil
user=> (clojure.string/split "name,address,city,state,zip,email,phone" #",")
["name" "address" "city" "state" "zip" "email" "phone"]```
    Making aliases is done simply by using a [[Clojure quote|quoted]] vector (shorthand for quoting every value inside it):
        ```clojure
user=> (require '[clojure.string :as string])
nil
user=> (string/capitalize "foo")
"Foo"```
    If I'd like to use functions from another namespace as if they were my own, I use the `:refer` keyword:
        ```clojure
(require 'clojure.string :refer [string])```
Preferred style, according to [[Stuart Sierra]]
    ```clojure
(ns com.example.my-application.server
  "Example application HTTP server and routing."
  (:refer-clojure :exclude [send])
  (:require
   [clojure.core.async :as async :refer [<! <!! >! >!!]]
   [com.example.my-application.base]
   [com.example.my-application.server.sse :as server.sse]
   [io.pedestal.http :as http]
   [io.pedestal.http.sse :as http.sse]
   [ring.util.response :as response])
  (:import
   (java.nio.file Files LinkOption)
   (org.apache.commons.io FileUtils)))```
Sources:
    [Clojure Libs and Namespaces: require, use, import, and ns](https://8thlight.com/blog/colin-jones/2010/12/05/clojure-libs-and-namespaces-require-use-import-and-ns.html)
    [How to ns](https://stuartsierra.com/2016/clojure-how-to-ns.html)
