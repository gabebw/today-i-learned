# Fix git submodule commits

When a submodule is checked out to an incorrect commit (for example, if you've
manually `cd`ed in and changed it), you can update it to what the superproject
expects by running:

    git submodule update

in the superproject.

For example, with this diff:

    $ git diff project/
    diff --git i/project w/project
    index 1328699fec..93bf78a26e 160000
    --- i/foo
    +++ w/foo
    @@ -1 +1 @@
    -Subproject commit 1328699fec60bc7cd388b073d0a086d4b2440209
    +Subproject commit 93bf78a26e5b509f95875936dd6e8e6f614d6e6c

Running `git submodule update` will snap the project back to
`1328699fec60bc7cd388b073d0a086d4b2440209`.
