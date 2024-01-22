# Rust Ownership System

This is REALLY hard to understand at first and some problems you run into will be because of Rust's `Borrow Checker`.
It exist because of safety reasons and you don't really need to understand exactly what it does.

But at a higher level, understanding how Rust checks the ownership of your variables can be a real life saver.

Ok, I said Rust doesn't have a garbage collector (unlike C++).<br>
I also said you don't need to allocate memory and free it. Why ?

That's because Rust follows a set of rules for variables, it keeps tracks of the data and where it is used in the program.

The borrow checker is able to determine where data needs to be initialized and where it needs to be freed (or dropped, in Rust terms).

It’s like it auto-inserts memory allocations and frees for you, giving you the convenience of a garbage collector with the speed and efficiency of manual management.

Now you understand all the jazz about mutability. But that also allows thing like Shadowing (look it up).

## Move, Borrow, Copy

In Rust, there are three main rules, a variable can be either :


### Moved

```rs
let s1 = String::from("hello");
let s2 = s1;
```
s1 was moved to s2, s1 is no longer valid.

### Borrowed :

```rs
fn main() {
    let mut x = 5;
    let y = &x;

    println!("{}", y);
    x = x + 1;
    println!("{}", x);
}
```
Borrowing a variable creates an ```immutable``` value.

### Copied :

```rs
let x = 5;
let y = x;
```
y is independent from x

### Ok ! I'll always copy my values :D
è_é NO.<br>
You WILL follow Rust ownership system and you WILL like it.

Your program won't be slower for simple data types, but when doing bigger projects, you'll hate yourself if you copy vectors (for example).

Ok, I'll explain to you when to copy, borrow or move. But don't worry, you can always come back to this workshop later to understand it better.

- Copy:

    Use Copy types when the size of the data is known at compile time and the data is cheap to copy.
    For simple scalar types like integers, booleans, characters, and fixed-size arrays, use Copy.

- Move:

    Use move semantics when you want to transfer ownership of a value to another variable or function.
    For types that involve dynamic memory allocation, such as String or Vec, use move semantics to avoid unintended cloning of potentially large data.

- Borrow:

    Use borrowing (references) when you want to allow multiple parts of your code to read or modify a value without taking ownership.
    Use immutable references (&T) when you only need read access, and use mutable references (&mut T) when you need to modify the value. (T means type)

Example for a Borrow :
```rs
let x = 5;
let y = &x;      // Immutable reference, read-only access.
let mut z = x;   // Mutable copy, not a reference.
let w = &mut z;  // Mutable reference, allows modification.
```
