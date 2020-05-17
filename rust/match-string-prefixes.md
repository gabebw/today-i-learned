# Match String Prefixes

If you want to match against the first character of a string, use `match` on a
slice:

```rust
// compass_direction may be "N", "S", "E", or "W"
let compass_direction = "N";
match &compass_direction[0..1] {
    "N" => println!("North"),
    "S" => println!("South"),
    "E" => println!("East"),
    "W" => println!("West"),
    _ => println!("Oops"),
}
```
