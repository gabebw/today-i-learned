# Parsing into anything with `.parse()`

Imagine parsing a custom type (not just a number) out of any string:

```rust
let foo: MyCustomType = string.parse();
```

You can implement that with `std::str::FromStr`:

```rust
impl std::str::FromStr for MyCustomType {
  // Set associated type - what type do we use if parsing fails?
  type Err = Error;

  fn from_str(s: &str) -> Result<Self, Self::Err> {
    let result = s.split(',').collect()[0].parse::<i32>()?;
    return Ok(s);
  }
}
```
