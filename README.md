# Incorrect use of free() in C

This repository demonstrates an example of a common error in C programming: attempting to free a pointer that was not allocated using `malloc` or `calloc`. This can lead to undefined behavior, such as program crashes or memory corruption. 

The `bug.c` file shows the erroneous code, while `bugSolution.c` provides a corrected version.

**Explanation:**

In C, memory allocated using `malloc` or `calloc` must be explicitly freed using `free()` to prevent memory leaks. However, pointers that are declared as automatic variables (like `ptr` in the buggy code) are allocated on the stack and are automatically freed when the function returns. Calling `free()` on such a pointer results in undefined behavior. 

**Solution:**

The corrected code avoids calling `free()` on the pointer `ptr` since it does not point to dynamically allocated memory.