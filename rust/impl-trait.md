# `impl trait`

I thought that the only way to specify "an object that implements Trait" was
`Box<dyn Trait>`. However, now I know that `impl Trait` works just as well if
you only ever pass one concrete type, without actually using dynamic dispatch.
Plus, using `impl Trait` saves a `Box` allocation too.

Documentation: https://doc.rust-lang.org/edition-guide/rust-2018/trait-system/impl-trait-for-returning-complex-types-with-ease.html
