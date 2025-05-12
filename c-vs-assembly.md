
Assembly can be embedded inside a C program, e.g.

```c
#include <stdio.h>

int main() {
  int a = 10, b = 5, result;
  asm("movl %1, %%eax; addl %2, %%eax; movl %%eax, %0"
    : "=r"(result)
    : "r"(a), "r"(b)
    : "%eax");
  printf("The value of a is: %d\n", result);

  return 1;
}

```

(table generated with an LLM, needs to be double checked)


| **Assembly Feature**           | **C Equivalent?**                                       | **Notes**                                       |
| ------------------------------ | ------------------------------------------------------- | ----------------------------------------------- |
| Arithmetic, logic, branching   | ✅ Yes                                                   | Directly supported in C                         |
| Memory access, pointers        | ✅ Yes                                                   | C gives pointer-level control                   |
| Registers                      | ❌ No (not directly)                                     | Register allocation is compiler-controlled      |
| Special CPU instructions       | ❌ Not always                                            | e.g., `cpuid`, SIMD, hardware interrupts        |
| Inline I/O with hardware ports | ❌ Needs inline assembly or platform-specific headers    | e.g., `outb`, `inb` on x86                      |
| Interrupt handlers, traps      | ❌ Needs platform-specific tools or assembly             | C can't define hardware ISRs portably           |
| Precise timing (e.g., `rdtsc`) | ❌ Often requires inline assembly or compiler intrinsics | Not exposed by standard C                       |
| Atomic operations              | ✅ Mostly                                                | Modern C11/C++11 and beyond provide atomic APIs |


## Can ASM access memory of another program?

In a typical user-space program, inline assembly (or any code) cannot directly access the memory of another program.

Modern operating systems (like macOS, Linux, Windows) enforce memory protection and virtual memory. Each process is given its own virtual address space, which is isolated from other processes.

The kernel ensures that processes cannot read or write to each other’s memory. If a process tries to access memory that doesn’t belong to it (i.e., a different process's memory), the OS will trigger a segmentation fault or access violation.

Memory allocation and protection are managed by the OS kernel. The kernel ensures that each program has its own private virtual address space, so one program cannot directly access another’s memory unless specific mechanisms (like inter-process communication) are used.



