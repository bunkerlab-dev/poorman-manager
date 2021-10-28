# poorman-manager

This tool is a set of scripts to make easier to install Python under GNU/Linux
x86 and x86_64. The tool includes:
* Access to basic OS information.
* Common interface to use the different package managers across GNU/Linux
  distributions (e.g. install, remove, update, clean).
* Custom scripts to compile certain libraries from source (e.g. OpenSSL, ffi).
* Thin wrapper around PyEnv to install Python versions, including:
  * all the preparation steps before calling `pyenv install` successfully, and
  * some cleanup after Python installation.

The tool adds a special focus in keeping the system as light as possible after
each command, since it is mainly used to build Docker images. This means that
it constantly takes care of removing unneeded files and folders (e.g. cache
and temporary files), so please **use it with caution** if you try it in your
personal computer.

## Usage

```
Usage: pmm <command> [<args>]

Valid pmm commands are:

    system      get relevant system information
    info        get relevant package information

    install     install a package
    remove      remove a package
    update      update the system package manager
    clean       clean the system package manager data

    enable      make a specific package available
    disable     make a specific package unavailable
```

## Known issues

For the Python installations, the following modules may fail:
* `_tkinter` module if `tk-dev` is not provided (e.g. Debian 4).
* `_uuid` module for Python 3.7+ if `uuid-dev` is not provided.
* `_sqlite3` module for Python 3.7+ if `libsqlite3-dev` version is elder than
  3.3.9 (e.g. Debian 4).
* `_sqlite3` module for Python 3.8+ if `libsqlite3-dev` version is elder than
  3.7.2 (e.g. Debian 5).

## License

```
Copyright (c) 2021 Víctor Molina García

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
