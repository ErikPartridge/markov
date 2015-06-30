# markov [![Build Status](https://travis-ci.org/aatxe/markov.svg?branch=master)](https://travis-ci.org/aatxe/markov) [![Crates.io](https://img.shields.io/crates/v/markov.svg)](https://crates.io/crates/markov) #

A generic implementation of a [Markov chain](https://en.wikipedia.org/wiki/Markov_chain) in Rust. 
Documentation can be found online [here](http://www.rust-ci.org/aatxe/markov/doc/markov/).

## Examples ##

With Strings: 
```rust
extern crate markov;

use markov::Chain;

fn main() {
    let mut chain = Chain::new();
    chain.feed_str("I like cats and I like dogs.");
    println!("{}", chain.generate_str());
}
```

With integers:
```rust
extern crate markov;

use markov::Chain;

fn main() {
    let mut chain = Chain::new();
    chain.feed(vec![1u8, 2, 3, 5]).feed(vec![3u8, 9, 2]);
    println!("{}", chain.generate());
}
```

Chains have iterators (both infinite and sized!):
```rust
extern crate markov;

use markov::Chain;

fn main() {
    let mut chain = Chain::new();
    chain.feed_str("I like cats and I like dogs.");
    for line in chain.iter_for(5) {
        println!("{}", line);
    }
}
```

## Contributing ##
Contributions to this library would be immensely appreciated. It should be noted that as this is a
public domain project, any contributions will thus be released into the public domain as well.
