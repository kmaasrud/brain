**Variables** in [[Rust]] are declared with the `let` keyword, for example:

```rust
let x = 5
```

### Variable shadowing

You can declare a variable with the same name as a previous variable by repeating the `let` keyword. This is called *shadowing*.

```rust
fn main() {
	let x = 5;
	let x = x + 1; // The old x is now shadowed by the new x
	
	println!("The value of x is: {}", x);
}
```

```
$ cargo run
   Compiling variables v0.1.0 (file:///projects/variables)
    Finished dev [unoptimized + debuginfo] target(s) in 0.31s
     Running `target/debug/variables`
The value of x is: 12
```

Shadowing is different from marking a variable as [[Mutability (Rust)|mutable]]. Shadowing creates an entirely new variable, just with the same name as a previous variable. This effectively makes the old variable's value inaccessible by succeeding code, but does not delete it.