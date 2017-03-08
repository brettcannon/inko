# Inko

**NOTE:** Inko is still a work in progress and in the very early stages. For
example, there's no website just yet, the compiler is in the super early stages,
etc.

Inko is a gradually typed, interpreted programming language that combines the
flexibility of a dynamic language with the safety of a static language. Inko
also combines elements from object oriented languages (e.g. classes and traits)
with elements from functional programming languages (e.g. immutability by
default).

Inko allows writing of concurrent programs without having to worry about locking
or data races. Furthermore Inko comes with a high performance garbage collector
based on [Immix][immix].

Inko borrows a lot of elements from other programming languages such as Ruby,
Smalltalk, Erlang/Elixir, and Python. Whitespace is used for indentation as it
leads to a good combination of compact and readable code. Inko does not feature
any special statements such as `if` or `switch`, instead almost everything is
implemented using methods (safe for a few keywords such as `class`).

## Examples

The venerable Hello World:

    import std::stdout

    stdout.print 'Hello, world!'

Concurrent Hello World:

    import std::stdout
    import std::process

    process.spawn {
      stdout.print 'Hello from process 1!'
    }

    process.spawn {
      stdout.print 'Hello from process 2!'
    }

For more examples see the Inko website.

## Requirements

* A UNIX system, Windows is currently not tested/supported

When working on Inko itself you'll also need:

* Rust 1.10 or newer using a nightly build (stable Rust is not supported)
* Cargo

The following dependencies are optional but recommended:

* Make
* Rustup

## Installation (for developers)

The easiest way to install Inko in case you want to hack on it is to first clone
the repository. Once cloned you'll need to build the VM and the compiler.

### Building The VM

To build the VM run the following:

    cd vm
    make

### Building The Compiler

To build the compiler, run the following:

    cd compiler
    make

[immix]: http://www.cs.utexas.edu/users/speedway/DaCapo/papers/immix-pldi-2008.pdf
