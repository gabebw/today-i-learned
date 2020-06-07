# Run Multiple Commands in an xargs stream

It's a bit gross, but here it is (from
[here](https://stackoverflow.com/questions/6958689/running-multiple-commands-with-xargs)):

```sh
xargs -n 1 sh -c 'for arg do echo "== BEFORE =="; main_command "$arg"; echo "== AFTER =="; done' _
```

Note that necessary underscore at the end.

This can be handy if you want to add logging around the `main_command`, or use
the same `$arg` for more than one command.

It's best to use null-terminated strings, too, so change newlines to null bytes
and tell xargs to look for them:

```sh
tr '\n' '\0' | xargs -0 ...
```

That `tr` snippet even works on macOS, which is sometimes finicky about matching
`\n`.
