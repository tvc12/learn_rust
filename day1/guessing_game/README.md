### guessing_game

+ Programming a Guessing Game 🦀 [docs](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html)

### Getting started

👉 Setting Up a New Project:

```bash
cargo new guessing_game
cd guessing_game
```

👉 Processing a Guess

Enter the code into `src/main.rs`

```rust
use std::io;

fn main() {
    println!("Guess the number!");

    println!("Please input your guess.");

    let mut guess = String::new();

    io::stdin()
        .read_line(&mut guess)
        .expect("Failed to read line");

    println!("You guessed: {}", guess);
}
```

👉 Run Project

```bash
cargo run

# Guess the number!
# Please input your guess.
# hello
# You guessed: hello
```
