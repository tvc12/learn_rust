### Hello cargo

+ Learn use cargo 🦀 [docs](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html#building-and-running-a-cargo-project)

👉 Create project `cargo new [name]`

Example:

```bash
cargo new hello_cargo
cd hello cargo
```

👉 Building and running a cargo project

```bash
cargo run
# -- OR --
cargo build
./target/debug/hello_cargo
```

🍵 We just built a project with cargo build and ran it with ./target/debug/hello_cargo

#### 👍 Recap

+ We can build a project using cargo build.
+ We can build and run a project in one step using cargo run.
+ We can build a project without producing a binary to check for errors using cargo check.
+ Instead of saving the result of the build in the same directory as our code, Cargo stores it in the target/debug directory.
