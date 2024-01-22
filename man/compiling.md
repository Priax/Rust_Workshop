# How to compile in Rust

To compile a Rust program, you can either use rustc, the rust compiler, or cargo.

`rustc test.rs` will output the `test` executable !
<br><br>
Cargo is a bit different, you can create a new project using `cargo new name_of_project`<br><br>
You'll get a new directoy named `name_of_project/` with a `cargo.toml` file, a `src` directory with a `main.rs`, you can run your program using `cargo run`, or build the executable using `cargo build`.

```toml
[package]
name = "name_of_project"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```

You can add any **crate** to a cargo.toml file, when running `cargo run`, cargo will fetch the repositories containing your dependencies with the specified version and features (you can also just use `cargo add name_of_crate`) !<br><br>

For example :

```toml
[dependencies]
dotenv = "0.15.0"
reqwest = "0.11.22"
serde = { version = "1.0.193", features = ["derive"] }
serde_json = "1.0.108"
serenity = { version = "0.12.0", features = ["model"] }
thiserror = "1.0.50"
tokio = { version = "1.35.0", features = ["macros", "rt-multi-thread"] }
sqlx = {version = "0.7.3", features = ["postgres", "runtime-tokio-rustls", "json"]}
futures = "0.3.29"
sqlx-core = "0.7.3"
```
<br>

But... I don't know any crate !<br>
Worry not, my friend : <a href="https://crates.io/" target="_blank"> Crates.io</a>

## Some useful crates

    1. Tokio, for asynchronous programs
    2. Serde, for parsing (YAML, JSON, XML...)
    3. SQLX, for databases
    4. Rocket, for web apps
    5. thiserror, for error management
