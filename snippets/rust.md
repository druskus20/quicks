# Rust snippets

#### [Bevy] Use closures to generate a system that receives an argument
```rust
fn make_print_function(string: &str) -> Fn() -> () {
  || println!(string)
}

App::build()
  .add_startup_system( make_print_function("hello").system() )
  .add_startup_system( make_print_function("world").system() )
  .run();

```

