# Functions

```rs
fn my_func(a: i32, b: i32) -> i32 {
    a + b
}

fn main() {
    println!("{}", my_func(1, 2));
}
```

\- You forgot a semicolon !<br>
\- No, I didn't.

In Rust, you can return in multiple ways, not adding a `;` means you return the value.

A function in Rust takes parameter, like in C, you specify the return value using `-> type`

Some other examples...

```rs
enum Color {
    Red,
    Yellow,
    Blue,
}

fn say_color(color: &Color) -> &'static str {
    match color {
        Color::Red => "red",
        Color::Yellow => "yellow",
        Color::Blue => "Blue",
    }
}

...

fn factorial(n: usize) -> usize {
    (1..=n).product()
}

pub fn open_image(file_path: &str) -> Result<Vec<(i32, i32, Color)>, String> {
    ...

    Ok(pixels)
}
```
This last function is complicated so I truncated it.
As you can see, it returns a Result with a Vector of two int and a Color and a string (This `Color` has nothing to do with the enum above by the way, it's from another of my program)

There are some keywords that are useful for error handling, like `Result` or `Option`, take a look at how to use them !

Obviously, a function can return nothing...
