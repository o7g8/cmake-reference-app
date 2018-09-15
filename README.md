# Guidelines

A reference project for building of a Windows C application with different tool-chains using the same codebase.

The examples use VS2017, MSYS2, and CMake.

## Command-line build

### Visual Studio Native Tools Command Prompt

Open e.g. `x64 Native Tools Command Prompt for VS 2017`:

```bat

cl /MD hello.c user32.lib

```

### cmd/MINGW

In `cmd` ensure your MINGW64 environment is in the path:

```bat

set PATH=d:\local\msys64\mingw64\bin;%PATH%

```

Works both in `msys2`, `mingw` and `cmd`

```bat

gcc hello.c -o hello.exe -mwindows

```

## Build with CMake

### MSYS2

```bash

mkdir build
cd build
cmake -G "MSYS Makefiles" ..
make

```

### cmd/MINGW

Execute in `cmd` with MINGW64 in the `PATH` (see above):

```bat

mkdir build
cd build
cmake -G "MinGW Makefiles" ..
mingw32-make

```

## References

* <http://mingw-cross.sourceforge.net/hello_win32api.html>

* <https://docs.microsoft.com/en-us/cpp/build/walkthrough-compile-a-c-program-on-the-command-line?view=vs-2017>