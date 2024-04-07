# Weird Language

Weird Language is a custom programming language created by Kamil Malicki in 2023/2024. It is designed for low-level system programming and educational purposes, offering direct interaction with hardware components.

## Installation (Windows):

To compile and execute Weird Language programs on Windows, download the compiler from the following link: [Weird Language Compiler](https://drive.google.com/file/d/1Yt9O33U0uUXcv2mGu9yhgsScRsKNNga0/view?usp=drive_link).
then you should copy the Weird directory to C:\ to avoid errors. All this from the installation can now be used from the wdc.exe compiler in the Weird\bin\ directory.

## How to Write Code:

To write code in Weird Language, follow these steps:

1. **Include the Library:** Begin your code by including the "Weird.h" library, which contains essential functions and definitions for the language.
2. **Define Constants and Variables:** Declare any necessary constants and variables, including stack size (`STACK_SIZE`) and registers.
3. **Write Instructions:** Compose your program using Weird Language's instructions, including input/output, arithmetic/logical operations, control flow, and interrupt handling.
4. **Compile and Execute:** After writing your code, compile it using the Weird Language compiler located at `Weird\bin\wdc.exe` and execute the generated binary.
   *SYNTAX: wdc.exe file_input_for_compilation file_output* outputs file this is for example .exe .obj .o .bin .hex e.t.c

## Features:

- **Registers:** AL, AH, BL, BH, CL, CH, DL, DH, SI
- **Stack Operations:**
  - `push(int value)`: Pushes the given value onto the stack.
  - `pop()`: Pops the top value from the stack.
- **Input/Output Functions:**
  - `out(char letter)`: Outputs a character to the console.
  - `in()`: Reads a character from the console.
- **Arithmetic Operations:**
  - `inc(int *value)`: Increments the value.
  - `dec(int *value)`: Decrements the value.
  - `neg(int *value)`: Negates the value.
  - `and(int *value, int mask)`: Performs bitwise AND operation.
  - `or(int *value, int mask)`: Performs bitwise OR operation.
  - `mov(int *variable, int value)`: Moves the value into the variable.
- **Control Flow:** 
  - `halt`: Halts program execution.
  - `nop`: No operation.
- **Interrupt Handling:** 
  - `interrupt(int num)`: Handles system interrupts.
  - `cli()`: Clears interrupt flag.
  - `sti()`: Sets interrupt flag.
- **Error Handling:** 
  - Error messages for stack overflow/underflow and unknown interrupt values.

## Purpose:

Weird Language serves as a tool for testing C language proficiency without relying on the standard library (`stdio.h`). It allows programmers to demonstrate their understanding of low-level system programming concepts and direct hardware interaction.

## Example Code:

Below is an example code snippet written in Weird Language:

```weird
#include <Weird.h>

void main(){
  out('H');
  out('e');
  out('l');
  out('l');
  out('o');
}
```
after typing wdc.exe file.c file.exe into cmd, you can simply run file.exe and you will get a response on the command line, in this case you will get `Hello` because out(); it allows you to display one letter, all stdio.h functions are disabled, that's why the language itself resembles the operations and the result of these operations of the assembler, that's why I called it Weird Language
