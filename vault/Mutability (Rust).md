All variables in [[Rust]] are [[Mutability (programming)|immutable]] by default. This is to prevent bugs related to an unexpected change, which can be hard to debug. However, mutability is supported and can be explicitly stated by using the `mut` keyword: 

```rust
let mut x = 5;
println!("The value of x is: {}", x);
x = 6;
println!("The value of x is: {}", x);
```

The above code will not throw a compile error, whilst omitting `mut` would have.

```
$ cargo run
   Compiling variables v0.1.0 (file:///projects/variables)
    Finished dev [unoptimized + debuginfo] target(s) in 0.30s
     Running `target/debug/variables`
The value of x is: 5
The value of x is: 6
```

Note that immutable variables in [[Rust]] are different from [[Constants (Rust)|Rust constants]].