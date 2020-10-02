[[Rust]] has two data type subsets: *scalar* and *compound*.

## Scalar types

There's four primary scalar types: *integers*, *floats*, *Booleans* and *characters*.

### Integers

| **Length** | **Signed** | **Unsigned** |
| --: | :--: | :--: |
| 8 bits | `i8` | `u8` |
| 16 bits | `i16` | `u16` |
| 32 bits | `i32` | `u32` |
| 64 bits | `i64` | `u64` |
| 128 bits | `i128` | `u128` |
| Depending on the architecture of the computer (64 or 32 bits) | `isize` | `usize` |

The default integer type is `i32`.

### Floating-point numbers

| **Length** | **Name** |
| --: | :--: |
| 32 bits | `f32` |
| 64 bits | `f64` |

The default float type is `f64`.

### Booleans and characters

| **Length** | **Name** |
| --: | :--: |
| (Probably 1 byte?) | `bool` |
| 4 bytes | `char` |

[[Rust]] is a [[Static type checking|statically typed]] language, which means it has to know all the types of each variable at compile time. 

## Compound types

Compound types group several values together into one type. There's *tuples* and *arrays*.

### Tuples

Tuples have a fixed length, but can contain different types. They are created by listing each value separated by a comma inside parentheses. In the below example, the values are bound to `tup` as a tuple type and can be accessed by *destructuring* (or *unpacking*, as its called in [[Python]]) it into other variables. 

```rust
let tup: (i32, f64, u8) = (500, 6.4, 1); // Types can be declared explicitly
let tup = (500, 6.4, 1); // Or they can be inferred by the compiler

let (x, y, z) = tup;

println!("The value of y is: {}", y);
```

You can also access the values of a tuple by index (starting at 0), like this

```rust
let x: (i32, f64, u8) = (500, 6.4, 1);

let five_hundred = x.0;

let one = x.2;
```

### Arrays

Arrays differ from tuples in that they require the same type for each element. They still have a fixed length. They are useful when you want your data allocated on the [[Stack (Rust)|stack]] rather than on the [[Heap (Rust)|heap]], or if you want to ensure a fixed number of elements. Arrays are declared by listing the elements out inside square brackets:

```rust
let months = ["January", "February", "March", "April", "May", "June", "July",
			  "August", "September", "October", "November", "December"];
```

or if you need to specify the type and number of elements:

```rust
let a: [i32; 5] = [1, 2, 3, 4, 5];
```

You can also fill an array of a specified length with the same item by the following syntax:

```rust
let a = [3; 5];
```

Accessing elements is done in the same syntax as [[Python]], namely using square brackets: `a[0]`.