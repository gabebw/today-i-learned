# Complete an argument with files in  a specific directory

The short version is that you use `_files -W`:

    _files -W /Users/gabe/code/personal/today-i-learned

That will only complete with files in that directory.

Here's a complete example that will complete the first argument of a command
using files from the given directory, and otherwise do nothing:

```zsh
# The details in til() aren't important, but it must be a function, not an
# alias, or else `compdef` won't do anything with it.
til(){
  local category=$1
  shift
  local name=$*
  name=${name// /-}
  vim "/Users/gabe/code/personal/today-i-learned/${category}/${name}"
}
_complete-first-file-argument() {
  if (( CURRENT == 2 )); then
    # We're on the first argument, complete it
    _files -W /Users/gabe/code/personal/today-i-learned
  else
    # Do nothing
  fi
}
compdef _complete-first-file-argument til
```
