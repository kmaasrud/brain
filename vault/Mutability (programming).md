**Mutability** refers to the ability to change a variable's state or content after its created. 

[[Python]] is an example of a programming language that has mutable variables as a default, without support for *immutable* variables. As an opposite example, [[Rust]] has immutable variables as the default and demands you explicitly specify the variable as mutable before any change can be done to it. This has several advantages, the key one being avoiding a scenario where one part of a codebase operates as if a variable keeps its value, while the other changes it. This can often be hard to track down when debugging. Mutating a large datastructure may also give performance benefits over copying and creating a new instance.

Sources:
- [[The Rust Programming Language]] - [Variables and mutability](https://doc.rust-lang.org/book/ch03-01-variables-and-mutability.html)
- [Wikipedia](https://en.wikipedia.org/wiki/Immutable_object)