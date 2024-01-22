# Error management in Rust
## Using Result to catch errors

```rs
#[derive(Debug)]
enum Version { Version1, Version2 }

fn parse_version(header: &[u8], index: usize) -> Result<Version, &'static str> {
    match header.get(index) {
        None => Err("invalid header length"),
        Some(&1) => Ok(Version::Version1),
        Some(&2) => Ok(Version::Version2),
        Some(_) => Err("invalid version"),
    }
}

fn main() {
    let version = parse_version(&[1, 2, 3, 4], 0);
    match version {
        Ok(v) => println!("working with version: {v:?}"),
        Err(e) => println!("error parsing header: {e:?}"),
    }
}
```

Try using this program and modifying the index value.
Rust has a `match` statement that lets you have different behaviour after a function.

This might be a bit complicated for a beginner though, but it's always useful to know !<br>
Here, Result return either a Ok(Version) or a Err(&'static str) (A string, representing the error message).

## Panic!

```rs
fn main() {
    panic!("I'm stopping right here.");
}
```

Pretty straightforward, you shouldn't use it often because it stops your program. But IF you need it, it's a good way to do it. <br>
Obviously, Rust programs can panic on their own.

```rs
fn main() {
    let numbers = ["Apple", "Banana", "Lemon"];

    for i in 0..=numbers.len() {
        let value = numbers[i];
        println!("Value at index {}: {}", i, value);
    }
}
```

## Options

```rs
fn divide(numerator: f64, denominator: f64) -> Option<f64> {
    if denominator == 0.0 {
        None
    } else {
        Some(numerator / denominator)
    }
}

fn main() {
    let result = divide(2.0, 3.0);
    println!("What if I don't match the result : {:?}", result);

    match result {
        Some(x) => println!("Result: {x}"),
        None    => println!("Cannot divide by 0"),
    }
}
```

For those that know Haskell, this is a bit like `Maybe`.
Returning an `Option` is simple and allows for better error management.
