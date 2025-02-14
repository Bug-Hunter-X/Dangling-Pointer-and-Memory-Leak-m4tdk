# Dangling Pointer and Memory Leak in C

This repository demonstrates a common error in C programming: attempting to free memory allocated on the stack.

## The Bug

The `bug.c` file contains code that allocates an integer variable `x` on the stack and then attempts to free its memory using `free()`. This is incorrect because `free()` is designed for heap memory allocated with `malloc()`, `calloc()`, or `realloc()`. Attempting to use it with stack memory results in undefined behavior, which can lead to program crashes or other unpredictable errors.

## The Solution

The `bugSolution.c` file corrects the issue. Since `x` is allocated on the stack, it doesn't require explicit freeing. The program simply modifies the value of `x` through the pointer `ptr`. 

## How to Compile and Run

1. Save `bug.c` and `bugSolution.c`.
2. Compile using a C compiler (like GCC):
   ```bash
gcc bug.c -o bug
gcc bugSolution.c -o bugSolution
```
3. Run the executable files:
   ```bash
./bug
./bugSolution
```