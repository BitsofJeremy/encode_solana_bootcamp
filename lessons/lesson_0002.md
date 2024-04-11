
# Lesson 2 links and more


The second session is now up on YT! You can check it out here:
https://youtu.be/bSEivS3yiBM

Instructor notes [they are detailed and have screenshots]:
 - [Instructor Notes](../instructor_slide_notes_and_homework/Lesson2.pdf)
 - [Homework](../instructor_slide_notes_and_homework/Homework2.pdf)



https://app.sli.do/event/9bhfXBfjYd6QpmY3g8tQLZ/live/questions


Proof of History Explained by a Water Clock
https://medium.com/solana-labs/proof-of-history-explained-by-a-water-clock-e682183417b8

Possible AI transscript for lesson
https://otter.ai/u/2DeTnr4B2epI1WTGefQKW9yMEII?utm_source=va_chat_link_1

Whiteboard Series with NEAR | Ep: 2 Anatoly Yakovenko from Solana
https://www.youtube.com/watch?v=rKGhbC6Uync

Solana white paper  [see page 3]
https://solana.com/solana-whitepaper.pdf


# Rust links

https://www.rust-lang.org/learn


https://rustbyexample.io/arrays


rustlings command line app:
https://github.com/rust-lang/rustlings

Rust Cookbook:
https://rust-lang-nursery.github.io/rust-cookbook/

Control flow from rust lang book:
https://doc.rust-lang.org/book/ch03-05-control-flow.html


_I should look up local LLM AI model for Rust_


https://web3.career/learn-web3/top-solana-open-source-projects#metaplex

Awesome Rust:
https://github.com/rust-unofficial/awesome-rust


## IDEs

Jetbrains Rustover
https://www.jetbrains.com/rust/nextversion/

VScode
https://code.visualstudio.com/

---


is there a OpenZeppelin equivalent?

for Solana Rust
https://www.anchor-lang.com

https://github.com/solana-labs/solana-program-library


---

### other


Blockchain IDE dev: Ziion VM


Neat question from the class:

```
İmran:
This is slightly on a tangent. But one thing id love to hear from you about is what things genuinely excite you in terms of what's possible with blockchain. Not the marketing bullcycle pitch we hear everywhere. But you personally with your depth of building experience and ideological affinity
```

---


# Homework 2

## Solana Ecosystem

1. How many validators are there currently?

```1,748```

Pulled from Solscan: https://solscan.io/validator


2. What is special about this block?

```This is the first block AKA the genesis block```

https://explorer.solana.com/block/0


3. What is special about this address?

```This is an Incinerator address for burning SOL```

https://explorer.solana.com/address/1nc1nerator11111111111111111111111111111111


4. What is this transaction doing?

```This tx is burning 11,365,066.99 SOL```

https://explorer.solana.com/tx/45pGoC4Rr3fJ1TKrsiRkhHRbdUeX7633XAGVec6XzVdpRbzQgHhe6ZC6Uq164MPWtiqMg7wCkC6Wy3jy2BqsDEKf


5. What is the largest balance you can find in an account?



6. What advantages will the end user see when using Solana compared to other blockchains?

```
1. High throughput
2. Low transaction fees
3. Fast confirmation times
4. Scalability
5. Growing ecosystem support
6. Developer-friendly environment
7. Security
8. Interoperability
```

7. Install Rust if needed.
  1. Follow these instructions for Mac / Linux
  2. See these instructions for Windows
  3. Alternatively use gitpod for a linux environment



### Installed Rust a while ago with Brew on MacOS:

https://www.petergirnus.com/blog/rust-macos-how-to-install


create `main.rs`

```rust
fn main() {
    println!("Hello World!");
}
```

Compile:

`rustc main.rs`


run:

```zsh
jeremy@mac lessons % ./main
Hello World!
```



### Add AI Summary



```
Encode x Solana Bootcamp Sponsored by the Solana Foundation Q1 2024

Proof of History (PoH) is a decentralized clock for blockchain scalability, explained by Speaker 1. PoH uses a decentralized clock to measure time accurately, allowing for faster block production and validation. Speaker 1 highlights the advantages of PoH, including more accurate time measurement, smaller timeouts, and higher throughput. In a separate conversation, Speaker 1 discusses the fundamental concepts of Rust, including immutable variables, data types, and control flow. They emphasize the importance of understanding Rust's control flow and data structures to write effective and efficient code, providing examples of how to use the `if` expression and the `elf` keyword.

Transcript

https://otter.ai/u/2DeTnr4B2epI1WTGefQKW9yMEII?view=transcript

Action Items
[ ] Review the 7 major innovations of Solana design.
[ ] Read through Solana proof of history documentation for more details.
[ ] Look at the article and water clock analogy to better understand proof of history if needed.
[ ] Take throughput numbers with a grain of salt, understand context and environment.
[ ] Get involved with Solana events if interested.
[ ] Start learning Rust, work through coding examples.
[ ] Ask questions about Rust in Discord or Slido.
[ ] Work through Rust exercises in teams.
Outline
Solana's innovative timekeeping system using Proof of History.
Solana's innovative Proof of History clock system helps coordinate events within a decentralized system.
Speaker 1 explains that hashing a sequence of inputs repeatedly can provide an upper bound on the time it takes for certain events to occur.
The hashing process can also provide a lower bound on time, as inserting a message into the sequence will change its output from that point on.
Decentralized clocks and leader selection.
Speaker 1 explains how proof of history can be used to create a decentralized clock that is secure and tamper-proof.
The system uses a sequence of hash values to create a proof of time, which can be verified in parallel to speed up the verification process.
Speaker 1 explains how a "proof of history" value can be used as a timestamp for events within a decentralized system, allowing for faster and more efficient consensus among nodes.
The mechanism for selecting a leader within the system depends on the amount of stake provided by validators, with more stake resulting in a higher likelihood of being chosen as a leader.
Proof of history and its advantages in blockchain technology.
Leader in decentralized system uses proof of history to accurately measure time, reducing timeouts and increasing block production speed.
Anatoly and his team developed Solana, a high-performance blockchain with fast transaction processing and the ability to link to other blockchains like Aetherium.
Salon, a blockchain-based platform with ups and downs.
Salon's history includes recovering from FTX and Solana's impact, and it's currently going well with a lot of events and opportunities for involvement.
Eunbi's work on Rust addresses memory safety issues by avoiding garbage collection, ensuring objects are not corrupted or written to by other processes.
Rust's unique approach to memory management allows for concurrent programming without performance issues, providing a more efficient and safe alternative to traditional languages.
Rust's default variables are immutable, but can be made mutable with the "mute" keyword.
Data types in Rust programming language.
Speaker 1 explains how to create compound data types in Rust, including tuples, arrays, and structs.
Speaker 1 demonstrates how to declare and use instances of these data types, including vectors.
Speaker discusses strings, arrays, and vectors in Swift programming language.
Rust arrays, slices, and immutability.
Speaker 1 explains that arrays in Rust are immutable by default, and their size cannot be changed once initialized.
Speaker 1 also highlights the importance of understanding array initialization and the use of the `new` keyword to make arrays mutable.
Speaker 1 explains that slices in Rust allow for more flexible access to arrays, enabling dynamic length and readable numeric literals.
The anchor framework and other deployment options will be explored for writing smaller contracts and deploying them on testing roads and Main Net.
Rust programming language features and best practices.
Speaker 1 explains Rust's noms, functions, and return types in a code block.
Speaker explains control flow statements in Python, including if/else statements and returns.
Speaker 1 explains how to use the `option` enum in Rust to handle return values with meaningful error handling.
Speaker 1 demonstrates how to use `option` to encapsulate the idea of a function returning a value or no value at all.
```

