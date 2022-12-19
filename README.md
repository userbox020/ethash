# Installing ethash on Windows:

Clone the project from github
Open \src\libethash\mmap_win32.c for editing
Add the following after the last #include statement
#pragma comment(lib, "Shell32.lib")
Open \src\python\core.c
Replace:
#include <alloca.h>
with:
#if defined(_WIN32) || defined(WIN32)
#include <malloc.h>
#else
#include <alloca.h>
#endif
Run the following in the source code main folder
setup.py install


[![Build Status](https://travis-ci.org/ethereum/ethash.svg?branch=master)](https://travis-ci.org/ethereum/ethash)
[![Windows Build Status](https://ci.appveyor.com/api/projects/status/github/debris/ethash?branch=master&svg=true)](https://ci.appveyor.com/project/debris/ethash-nr37r/branch/master)

# Ethash

For details on this project, please see the Ethereum wiki:
https://github.com/ethereum/wiki/wiki/Ethash

### Coding Style for C++ code:

Follow the same exact style as in [cpp-ethereum](https://github.com/ethereum/cpp-ethereum/blob/develop/CodingStandards.txt)

### Coding Style for C code:

The main thing above all is code consistency.

- Tabs for indentation. A tab is 4 spaces
- Try to stick to the [K&R](http://en.wikipedia.org/wiki/Indent_style#K.26R_style),
  especially for the C code.
- Keep the line lengths reasonable. No hard limit on 80 characters but don't go further
  than 110. Some people work with multiple buffers next to each other.
  Make them like you :)
