# Fix Documentation: Arena Build Issue

## Issue Description
When running `make Arena`, the build failed with the following error:
```
make: clang++: No such file or directory
```

## Diagnosis
The `Makefile` was hardcoded to use `clang++` as the C++ compiler. However, `clang++` is not installed or available in the system's path. The system uses `g++` (GNU C++ Compiler) instead.

## Resolution
The `Makefile` was modified to use `g++` instead of `clang++`.

**Changes made to `Makefile`:**
```diff
- CC=clang++
+ CC=g++
```

## Verification
1. Ran `make Arena`.
2. Compilation succeeded without errors.
3. Verified the executable `./Arena` runs and displays its help message.

## How to Build
To build the project now, simply run:
```bash
make Arena
```
Or to build the counter tool:
```bash
make Arena_counter
```
