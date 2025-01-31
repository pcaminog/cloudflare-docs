---
pcx_content_type: content
title: Standard Library
weight: 3
meta:
  title: Standard Library provided to Python Workers
---

# Standard Library

Workers written in Python are executed by [Pyodide](https://pyodide.org/en/stable/index.html).

Pyodide is a port of CPython to WebAssembly — for the most part it behaves identically to [CPython](https://github.com/python) (the reference implementation of Python — commonly referred to as just "Python"). The majority of the CPython test suite passes when run against Pyodide. For the most part, you shouldn't need to worry about differences in behavior.

The full [Python Standard Library](https://docs.python.org/3/library/index.html) is available in Python Workers, with the following exceptions:

## Modules with limited functionality

- `hashlib`: Hash algorithms that depend on OpenSSL are not available by default.
- `decimal`: The decimal module has C (\_decimal) and Python (\_pydecimal) implementations
  with the same functionality. Only the C implementation is available (compiled to WebAssembly)
- `pydoc`: Help messages for Python builtins are not available
- `webbrowser`: The original webbrowser module is not available.

## Excluded modules

The following modules are not available in Python Workers:

- curses
- dbm
- ensurepip
- fcntl
- grp
- idlelib
- lib2to3
- msvcrt
- pwd
- resource
- syslog
- termios
- tkinter
- turtle.py
- turtledemo
- venv
- winreg
- winsound

The following modules can be imported, but are not functional due to the limitations of the WebAssembly VM.

- multiprocessing
- threading
- sockets

The following are present but cannot be imported due to a dependency on the termios package which has been removed:

- pty
- tty
