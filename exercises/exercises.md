# Exercises

Some simpler exercises in Rust you can do are those of `Rustlings` : https://github.com/rust-lang/rustlings/tree/main

I made the next exercises, they range from simple to very hard (for a beginner, at least).
You won't be able to finish those exercises, but you can always come back here if you want a challenge.

Also, those exercises are very easy to do with any AI assistant, I know that.
That's not the goal of this workshop. You should always try  to solve a problem yourself at first, else you won't learn the basics that are really important.

## Exercise 1 :

```rs
//Your task is to create a `Vec` which holds the exact same elements as in the array `a`.

fn array_and_vec() -> ([i32; 4], Vec<i32>) {
    let a = [10, 20, 30, 40]; // a plain array
    let v = // TODO: declare your vector here with the macro for vectors

    (a, v)
}
```

## Exercise 2 :

Read from a file and print its content.

> [!NOTE]
> `use std::fs;`

## Exercise 3 :

Make a function that takes two number and a string and matches the character to perform an operation. (+, -, *, /, %)

## Exercise 4 :

Add error handling to your program, to avoid dividing by zero. (%, /) <br>

> [!NOTE]
> `Option<T>` <br>
> (T means type, it can be anything you want)


## Exercise 5:

Write a program that prompts the user to input a string and then prints the reverse of that string. <br>

> [!NOTE]
> `use std::io::{self, Write};`

## Exercise 6:

Implement a function that checks whether a given string is a palindrome (reads the same backward as forward).

## Exercise 7 :

Create a simple struct representing a geometric point in 2D space. Implement a method for the struct that calculates the distance between two points.

> [!NOTE]
> `d=√((x2 – x1)² + (y2 – y1)²)`<br>
> (Also, use floats like `f64`, as it will be simpler)

## Exercise 8 :

Write a function that takes a vector of integers and returns a new vector containing only the unique elements (remove duplicates).

## Exercise 9 :

Implement a basic stack data structure. Create methods for pushing, popping, and checking if the stack is empty.

> [!NOTE]
> `.push()`<br>
> `.pop()` <br>
> `.is_empty()`

Using a Vector might be wise...

## Exercise 10 :

The newly-improved calibration document consists of lines of text; each line originally contained a specific calibration value that the Elves now need to recover. On each line, the calibration value can be found by combining the first digit and the last digit (in that order) to form a single two-digit number.

For example:
```
1abc2
pqr3stu8vwx
a1b2c3d4e5f
treb7uchet
```

In this example, the calibration values of these four lines are 12, 38, 15, and 77. Adding these together produces 142.
Consider your entire calibration document. What is the sum of all of the calibration values?

To begin, look at the `input.txt` file.

> [!NOTE]
> `.filter`<br>
> `format!("{}{}", ...);` <br>
> `.next()` <br>
> `.last()`

BONUS: If you're really good, this file also contains numbers written in letters (one, two... nine).
Consider them as actual number, do the sum of the calibration values.

An example if you need it... This should produce 281. <br>
29 + 83 + 13 + 24 + 42 + 14 + 76
```
two1nine
eightwothree
abcone2threexyz
xtwone3four
4nineeightseven2
zoneight234
7pqrstsixteen
```

## Exercise 11 :

Implement a basic concurrent program using Rust's `std::thread` and `std::sync::mpsc;` modules. For example, create a program that spawns two threads and prints the message sent from thread1 to thread2.

Networking is fun, you should try it out.
