## Typing in Rust

To create a variable in Rust, you use the `let` keyword, all variables are immutable by default (you can't modify them).
We'll see what it means in the next chapter.

You can't assign a value of a type to another type without running into a compilation error.

```rs
fn main() {
    let test: i32 = 42;
    println!("Bonjour Noa !");
    let value: u32 = test;

    println!("Your value is: {}", value);
}
```
```sh
error[E0308]: mismatched types
 --> workshop.rs:4:22
  |
4 |     let value: u32 = test;
  |                ---   ^^^^ expected `u32`, found `i32`
  |                |
  |                expected due to this
  |
help: you can convert an `i32` to a `u32` and panic if the converted value doesn't fit
  |
4 |     let value: u32 = test.try_into().unwrap();
  |                          ++++++++++++++++++++

error: aborting due to previous error

For more information about this error, try `rustc --explain E0308`.
```

> As you can see, the compiler gives you useful informations, it's going to become your best friend.
> Sometimes, it can be hard to understand those errors, but don't worry, it gets better with time.

You can also let the compiler infer the type at compile time, but it won't always work.
It's always a good pratice to give a type to your variables (it matters !)
