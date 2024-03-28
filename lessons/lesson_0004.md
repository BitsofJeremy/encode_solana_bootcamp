# Lesson 4 Notes and Links











# Fizz Buzz in Rust

see `fizzbuzz.rs` and `fizzbuzz`.


run with `./fizzbuzz`


#### Code

```rust
fn main() {
    for num in 1..=100 {
        if num % 3 == 0 && num % 5 == 0 {
            println!("FizzBuzz");
        } else if num % 3 == 0 {
            println!("Fizz");
        } else if num % 5 == 0 {
            println!("Buzz");
        } else {
            println!("{}", num);
        }
    }
}
```




