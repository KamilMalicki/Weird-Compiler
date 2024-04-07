## Common Interrupts

1. **Interrupt 0x10: Video Services**
   - Handles video-related operations.
   - Used for tasks like setting screen resolution and cursor positioning.
   - When `AH` register is equal to `0x00`, it sets the video mode. `AL` =  resolution type.
   - When `AH` register is equal to `0x0e`, it displays a character at the specified cursor position. `DL` = row, `DH` = column.

2. **Interrupt 0x15: System Services**
   - Provides system-level services, such as memory allocation and disk access.
   - When `AH` register is equal to `0x86` and `AL` is nonzero, it delays for a specified number of milliseconds.

3. **Interrupt 0x16: Keyboard Services**
   - Handles keyboard input and related operations.
   - When `AH` register is equal to `0x00`, it reads a character from the keyboard. `AL` is a key pressed from keyboard. 

## Implementing Interrupt Handling

To implement interrupt handling in a program:

1. **Define Interrupt Handlers**: Write functions to handle specific interrupts.

2. **Register Interrupt Handlers**: Register the handlers with the system or hardware.

3. **Enable Interrupts**: Allow the CPU to respond to incoming signals.

4. **Handle Interrupts**: Implement logic to respond to interrupts in the program.

5. **Set Up Interrupt Registers**: Configure the interrupt registers to specify which interrupts to handle and how to handle them. This includes setting up appropriate values in registers such as `AH`, `AL`, `BL`, `BH`, `CL`, `CH`, `DL`, `DH`, and `SI` according to the requirements of each interrupt service.

## Function Descriptions

### `out(char letter)`
- Prints a character to the standard output.
``` example
out(var1);
out('H');
```

### `in()`
- Reads a character from the standard input.
``` example
var1 = in();
```

### `inc(int *value)`
- Increments the value pointed to by the given pointer.
``` example
inc(*var1);
```

### `dec(int *value)`
- Decrements the value pointed to by the given pointer.
``` example
dec(*var1);
```

### `neg(int *value)`
- Negates the value pointed to by the given pointer.
``` example
neg(*var1, 5);
```

### `and(int *value, int mask)`
- Performs a bitwise AND operation between the value pointed to by the given pointer and a mask.
``` example
and(*var1, 5);
```

### `or(int *value, int mask)`
- Performs a bitwise OR operation between the value pointed to by the given pointer and a mask.
``` example
or(*var1, 5);
```

### `mov(int *variable, int value)`
- Moves the given value into the memory location pointed to by the given pointer.
``` example
mov(*var1, 5);
```

### `push(int value)`
- Pushes a value onto the stack.
``` example
push(54);
push('H');
```

### `pop()`
- Pops a value from the stack.
``` example
var1 = pop();
```

### `nop()`
- No operation (does nothing).
``` example
nop();
```

### `flag()`
- Prints the values of the interrupt flags (`interrupt_error` and `interrupt_flag`).
``` example
flag();
```


### `halt()`
- Halts the program execution indefinitely.
``` example
halt();
```

### `interrupt(int num)`
- Handles software interrupts based on the specified interrupt number.
``` example
sti();
AH = 0x00;
interrupt(0x16);
```

### `cli()`
- Clears the interrupt flag, disabling interrupts.
``` example
cli();
```

### `sti()`
- Sets the interrupt flag, enabling interrupts.
``` example
sti();
```

### `cls()`
- Clears the console screen.
``` example
cls();
```
