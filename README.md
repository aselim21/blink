# blink

A small Hello World Rust application for the AVR.

The program itself toggles a LED on PORTB periodically.

Designed for the ATmega328p.

[The AVR-Rust Book](https://book.avr-rust.com/)

## Prerequisites

  * A recent version of the nightly Rust compiler. Anything including or greater than `rustc 1.47.0-nightly (0820e54a8 2020-07-23)` can be used.
  * The rust-src rustup component - `$ rustup component add rust-src`
  * AVR-GCC on the system for linking
  * AVR-Libc on the system for support libraries

## Usage


Now to build, run:

```bash
rustup override set nightly

# Ensure time delays are consistent with a 16MHz microcontroller.
//for unix
export AVR_CPU_FREQUENCY_HZ=16000000 
//for windows terminal
set AVR_CPU_FREQUENCY_HZ=16000000 

# Compile the crate to an ELF executable.
cargo build -Z build-std=core --target avr-atmega328p.json --release

```
There should now be an ELF file at `target/avr-atmega328p/release/blink.elf`. It
can be flashed directly to an AVR microcontroller or ran inside a simulator.


## Resources

  * The [AVR-Rust book](https://book.avr-rust.com)

