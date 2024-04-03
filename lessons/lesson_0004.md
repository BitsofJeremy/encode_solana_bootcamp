# Lesson 4 Notes and Links


see instructor notes as they are detailed and have screenshots:

[Instructor Notes](../instructor_slide_notes_and_homework/Lesson4.pdf)


[Homework](../instructor_slide_notes_and_homework/Homework4.pdf)

*update*

[Homework Answers](../instructor_slide_notes_and_homework/Homework4Answers.pdf)


Slido:
https://app.sli.do/event/9bhfXBfjYd6QpmY3g8tQLZ/live/questions


AI summary link:
https://otter.ai/u/FU0Jx6tijoqrBOowUsh26UhqRqY?utm_source=va_chat_link_1


Add Let's Get Rusty Cheat Sheet:
[Link](LGR_Cheat_Sheet.pdf)



Regex Crate: https://docs.rs/regex/latest/regex/


TODO: See Borsch for serialization...



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




