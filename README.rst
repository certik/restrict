Restrict
========

The restrict library restricts the ``open()``, ``open64()`` and ``fopen()``
calls to only allow opening "allowed" files. Compile with::

    ./compile

Examples of usage::

    LD_PRELOAD=./restrict.so touch test_file
    LD_PRELOAD=./restrict.so cat test_file

How it Works
------------

It preloads the ``open()``, ``open64()`` and ``fopen()`` libc calls using the
``LD_PRELOAD`` mechanism. This means that static binaries, as well as accessing
files by other means than through ``open/open64/fopen`` will not be checked.

License
-------

All code in this package is released under the MIT license.
