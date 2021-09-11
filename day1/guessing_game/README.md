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

    let mut guess = String::new(); //created a mutable variable

    io::stdin()
        .read_line(&mut guess) // handle to get input from the user
        .expect("Failed to read line"); // cover error

    println!("You guessed: {}", guess); // {} as little crab pincers that hold a value in place
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

👉 Add random package

```toml
[dependencies]
# insert here
rand = "0.8.3"
```

👉 Get new package

```bash
cargo build
```

👉 Add Random Code

```rust
use std::io;
// -- new code here --
use rand::Rng; //The Rng trait defines methods that random number generators implement

fn main() {
    println!("Guess the number!");

    // -- new code here --
    let secret_number = rand::thread_rng().gen_range(1..101); //random a number between 1 and 100
    println!("The secret number is: {}", secret_number);
    // -----------------

    println!("Please input your guess.");

    let mut guess = String::new();

    io::stdin()
        .read_line(&mut guess)
        .expect("Failed to read line");

    println!("You guessed: {}", guess);
}
```

👉 Complete code

```rust
use std::io;
use rand::Rng;
// -- new code here --
use std::cmp::Ordering;

fn main() {
    println!("Guess the number!");

    let secret_number = rand::thread_rng().gen_range(1..101);

    println!("The secret number is: {}", secret_number);

    println!("Please input your guess.");

    let mut guess = String::new();

    io::stdin()
        .read_line(&mut guess)
        .expect("Failed to read line");

    // -- new code --
    let guess: u32 = guess
        .trim() // The trim method on a String instance will eliminate any whitespace at the beginning and end
        .parse() // The parse method on strings parses a string into some kind of number.
        .expect("Please type a number!");
    // -----------------

    println!("You guessed: {}", guess);

    // -- new code --
    match guess.cmp(&secret_number) { // the cmp method compares two values and can be called on anything that can be compared
        Ordering::Less => println!("Too small!"),
        Ordering::Greater => println!("Too big!"),
        Ordering::Equal => println!("You win!"),
    }
    // -----------------
}
```
