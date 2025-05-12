# Learn Programming

**Program**: *Input* -> *Computation* -> *Output*.

```
output = f(input)
```

C is effectively Assembly with syntactic sugar. C + Compiler/Assembler? = Assembly/machine code

Assembler vs compiler

## Curriculum

- Basic CLI skills
  - Learn vim
  - PATH environment variable
  - Variables in the CLI
  - Compile a basic C program with GCC
- Operating System Development
  - https://wiki.osdev.org/Bare_Bones
  - https://pdos.csail.mit.edu/6.828/2018/schedule.html – Operating System Design MIT https://pdos.csail.mit.edu/6.828/2018/lec/l-x86.pdf
- Network Programming
  - What is UDP? 
  - Writing a TCP server in C
  - Protocol design
  - https://web.mit.edu/2.993/www/lectures/lecture5.html 
- Hardware Design

## Vertical Stack Learning

Start with practical CRUD app development while looping back to computer science essentials.

What is the destination, and what is the journey? From what are we starting with?

## Code Examples

**`main.c`**

```c
int main() {
  return 1;
}
```

**`hello.c`**

```c
int main(int argc, char *argv[]) {
  printf("Hello, World!\n");
}
```

```sh
man 3 printf
```


**Compiling a C program**

```sh
gcc hello.c -o hello -Wall
```

## Architecture

(borrow concepts from the architecture world)

- https://www.youtube.com/watch?v=5avcps3bjlk – Design Thinking: How to Think Like an Architect (Roberts Architecture)

> Research -> Problem Definition -> Developing Alternatives -> Evaluating Alternatives -> Selection -> Communication

## Design

(borrow concepts from the product design world)


## Resources

- https://www.youtube.com/watch?v=N2bXEUSAiTI - what is programming (noob lessons!)
- LiveOverflow – https://www.youtube.com/watch?v=JGoUaCmMNpE – Writing a simple Program in C
- https://github.com/geohot/fromthetransistor
