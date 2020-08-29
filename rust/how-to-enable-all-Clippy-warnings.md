# How to enable all Clippy warnings

Add this to `main.rs`:

```rust
#![warn(clippy::all, clippy::pedantic)]
```
