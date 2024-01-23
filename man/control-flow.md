# Control Flow

## Conditions

Conditions in C and Rust are very similar, you don't need to add parenthesis though.
```rs
fn main() {
    let value: i32 = -42;

    if value < 0 {
        println!("This is a negative value...");
    } else if value > 0 {
        println!("This is a positive value...");
    } else {
        println!("This is... zero !");
    }
}
```

## Loops

```rs
fn main() {
    let mut sum = 0;
    for n in 1..101 {
        sum += n;
    }
    println!("{}", sum);
    println!("{}", (1..101).fold(0, |x, y| x + y));
}
```

Ok... What's this ?
mut ? 1..101 ??? fold ????

Calm down... Let's keep things simple.
First, here is the result of this program :
```bash
Priax@fedora-39:~/Projets_perso/RUST/workshop$ ./workshop
5050
5050
```

A for loop in Rust isn't complicated, just your starting value, 1, and your last value 101 (excluded).
You can also loop over `vec` (vectors), lists etc...

Here is an example with a vector and a list :
```rs
let v = vec![1, 2, 3];
for i in v.iter() {
    println!("{}", i);
}

let l = [4, 5, 6];
for i in l {
    println!("{}", i);
}
```

### Mutable, Immutable...

Okay, now, what's a mutable variable ?
> In Rust, a variable can be marked as mutable (using the mut keyword). This allows you to create mutable references to that variable. Mutable references allow you to modify the value they are pointing to.

If you know C, this should be easy to understand, if you don't, just consider a mutable variable can be modified, while an immutable variable can't.

### The FUN in FUNctional
For those that know Haskell, fold is easy to understand, for others, it may not be that simple. <br>
Rust is not a functional programming language per se, but it does have some functional elements (Immutability, data types using `struct` and `enum`, pattern matching using `match`, `impl` to implement your own traits...)

I won't delve deeper into those, but they are REALLY useful and you should learn how to use them if you want to learn Rust.

Fold is simple, it applies a function to each elements of an iteration, accumulating them into a new value.

You can find this way of programming complicated, but sometimes, thinking about a problem differently can help finding new ways of solving a problem.
