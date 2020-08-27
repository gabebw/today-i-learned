# Variably pad rust format strings

`format!` only takes a literal format string, so how do you left-pad something
to N width when N is variable?

Use this syntax:

```rust
let width = 20;
let s = "Hello there"
// result is: "Hello there         "
let result = format!("{:<width$}", &string, width = my_width)
```

The trailing `$` is important: instead of `20`, you write `VARIABLE_NAME$`.
