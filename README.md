# cpp-coverage
all details about cpp coverage

# Coverage Compile options

compile source code with GCC coverqge flags:

GCC Option Document: https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html

* add `-fprofile-arcs`, `-ftest-coverage` and `-g` flags
* or `--coverage` which inlcudes `-fprofile-arcs`, `-ftest-coverage` and `-g`
* for MC/DC coverage, add `-fcondition-coverage`, supported by GCC version >= 14.2+ 
    * https://gcc.gnu.org/onlinedocs/gcc-14.2.0/gcc/Instrumentation-Options.html

config in CMakeLists.txt 

set a `COVERAGE_COMPILER_FLAGS` variable

if gcc version < 14:

```
set(COVERAGE_COMPILER_FLAGS "-g -fprofile-arcs -ftest-coverage")
```

if gcc version >= 14.2:

```
set(COVERAGE_COMPILER_FLAGS "-g -fprofile-arcs -ftest-coverage -fcondition-coverage")
```

and then set c and cxx flags

```
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${COVERAGE_COMPILER_FLAGS}")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${COVERAGE_COMPILER_FLAGS}")
```

Now, for all cpp files are compiled, it will generate a corresponding `.gcno` file

# gcov

all details about gcov

* [GCC Gcov Document](https://gcc.gnu.org/onlinedocs/gcc/Gcov.html)

How to use:

    

# lcov

all details about lcov

# gcovr

all details about gcovr

# gtest

all details about gtest

# mock

all details about cpp unittest mock


