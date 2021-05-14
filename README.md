# Monty Interpreter
Monty 0.98 is a scripting language that is first compiled into Monty byte codes (Just like Python). It relies on a unique stack, with specific instructions to manipulate it. The goal of this project is to create an interpreter for Monty ByteCodes files.

## Monty byte code files
Files containing Monty byte codes usually have the .m extension. Most of the industry uses this standard but it is not required by the specification of the language. There is not more than one instruction per line. There can be any number of spaces before or after the opcode and its argument:
```
julien@ubuntu:~/monty$ cat -e bytecodes/001.m
push 0 Push 0 onto the stack$
push 1 Push 1 onto the stack$
$
push 2$
  push 3$
                   pall    $
$
$
                           $
push 4$
$
    push 5    $
      push    6        $
$
pall This is the end of our program. Monty is awesome!$
julien@ubuntu:~/monty$
luisdev@ubuntu:~/monty$ cat -e bytecodes/000.m
push 0$
push 1$
push 2$
  push 3$
                   pall    $
push 4$
    push 5    $
      push    6        $
pall$
luisdev@ubuntu:~/monty$
```
Monty byte code files can contain blank lines (empty or made of spaces only, and any additional text after the opcode or its required argument is not taken into account:
```
luisdev@ubuntu:~/monty$ cat -e bytecodes/001.m
push 0 Push 0 onto the stack$
push 1 Push 1 onto the stack$
$
push 2$
  push 3$
                   pall    $
$
$
                           $
push 4$
$
    push 5    $
      push    6        $
$
pall This is the end of our program. Monty is awesome!$
luisdev@ubuntu:~/monty$
```
##  Getting Started
* Ubuntu 14.04 LTS - Operating system reqd.
* GCC 4.8.4 - Compiler used

## Prerequisites
* Must have git installed.
* Must have repository cloned.
```
$ sudo apt-get install git
```
## Installing and Usage.
Clone the repository into a new directory:
```
$ git clone https://github.com/luisdev20/monty.git
```
Compile with the following:
```
gcc -Wall -Werror -Wextra -pedantic *.c -o monty
```
Run the interpreter on a file:
```
./monty bytecode_file
```
## > Available Monty Opcodes
- [x] push
 * Usage: push <int>
 * Pushes an element to the stack.
 * The parameter <int> must be an integer.
- [x] pall
 * Prints all values in the stack/queue, starting from the top.
- [x] pint
 * Prints the top value of the stack/queue.
- [x] pop
 * Removes the top element of the stack/queue.
- [x] swap
 * Swaps the top two elements of the stack/queue.
- [x] nop
 * Does not do anything.
- [x] add
 * Adds the top two elements of the stack/queue.
 * The result is stored in the second element from the top and the top element is popped.
- [x] sub
 * Subtracts the top element of the stack/queue from the second element from the top.
 * The result is stored in the second element from the top and the top element is removed.
- [x] mul
 * Multiplies the top two elements of the stack/queue.
 * The result is stored in the second element from the top and the top element is removed.
- [x] div
 * Divides the second element from the top of the stack/queue by the top element.
 * The result is stored in the second element from the top and the top element is removed.
- [x] mod
 * Computes the modulus of the second element from the top of the stack/queue divided by the top element.
 * The result is stored in the second element from the top and the top element is removed.
- [ ] pchar
 * Prints the character value of the top element of the stack/queue.
 * The integer at the top is treated as an ASCII value.
- [ ] pstr
 * Prints the string contained in the stack/queue.
 * Prints characters element by element until the stack/queue is empty, a value is 0, or an error occurs.
- [ ] rotl
 * Rotates the top element of the stack/queue to the bottom.
- [ ] rotr
 * Rotates the bottom element of the stack/queue to the top.
- [ ] stack
 * Switches a queue to stack mode.
- [ ] queue
 * Switches a stack to queue mode.
