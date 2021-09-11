### Variables and Mutability

+ Let’s explore how and why Rust encourages you to favor immutability and why sometimes you might want to opt out
+ 👍 Document in [here](https://doc.rust-lang.org/book/ch03-01-variables-and-mutability.html#variables-and-mutability)

### 🦀 Getting start

👉 When a variable is **immutable**, once a value is bound to a name, you can’t change that value

```rust
fn main() {
    let x = 5;
    println!("The value of x is: {}", x);
    x = 6; // <- error: "cannot assign twice to immutable variable"
    println!("The value of x is: {}", x);
}
```

👉 Variables are **immutable** only by **default**

👉 You can make them mutable by adding `mut` in front of the variable name

```rust
fn main() {
    let mut x = 5;
    println!("The value of x is: {}", x);
    x = 6;
    println!("The value of x is: {}", x);
}
```

### ⚠ Differences Between Variables and Constants

💥 You aren’t allowed to use `mut` with constants.

🦀 You declare constants using the `const` keyword instead of the `let` keyword, **and the type of the value must be annotated**.

```rust
const MAX_POINTS: u32 = 100_000;
```

🍵 Constants can be declared in any scope, including the global scope.

👍 Constants may be set only to a constant expression, not the result of a function call or any other value that could only be computed at runtime.

### ♥ Shadowing

👉 We can shadow a variable by using the same variable’s name and repeating the use of the `let` keyword

```rust
fn main() {
    let x = 5;

    let x = x + 1; // The first variable (x) is shadowed by the second

    let x = x * 2;

    println!("The value of x is: {}", x); // The value of x is: 12
}
```

👉 We can change the type of the value but reuse the same name.

```rust
fn main() {
    let spaces = "   ";
    let spaces = spaces.len();    
}
```
