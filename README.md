mknewfile
=========

Shell tool to create new files ( {ba,da,}sh compatible ) (version 0.1.0)

- [Usage](#usage)
- [License](#license)


Usage
-----

    mknewfile DESIREDPATH [BASEFORMAT]

Create a file and print its name. *DESIREDPATH* is the file path to create, if the
file already exists, it restarts the operation after changing the file basename
thanks to *BASEFORMAT* (defaults to `${name}_$i$ext`).

*BASEFORMAT* is evaluated in a subshell to control the file basename.
Example:

    $ touch foo.txt
    $ mknewfile foo.txt 'basename: $basename, name: $name, ext: $ext, i: $i'
    basename: foo.txt, name: foo, ext: .txt, i: 1

Usage example:

    $ test -e hello.txt ; echo $?
    0
    $ test -e hello_1.txt ; echo $?
    1
    $ mknewfile hello.txt
    hello_1.txt
    $ test -e hello_1.txt ; echo $?
    0


License
-------

> Copyright (c) 2017 Tristan Cavelier <t.cavelier@free.fr>

> This program is free software. It comes without any warranty, to
> the extent permitted by applicable law. You can redistribute it
> and/or modify it under the terms of the Do What The Fuck You Want
> To Public License, Version 2, as published by Sam Hocevar. See
> the COPYING file for more details.
