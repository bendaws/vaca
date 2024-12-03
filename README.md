# STS
STS is a stack-based interpreted language that looks like BASIC. The name comes from a mix of **ST**ACK and BA**S**IC.

- [Example](#example)
- [Language](#language)
  - [Commands](#commands)
  - [Symbols](#symbols)

# Example
```
PRM,STS_SHELL
STK
WHILE,+++
  WRT,shell > ,
  SET,CMD,<<<
  
  IF,$CMD,exit
    ESC
  IF,$CMD,hello
    WRT,hello
RET

END,0
```

# Language
## Commands
There is a list of 6 commands. Here is a list of them:

| Command   | Description             | Example   |
|-----------|-------------------------|-----------|
| ``RET``   | Release the current stack | ``RET`` |
| ``WRT``   | Print text to the screen | ``WRT,hello world``|
| ``WRT``   | ^  You may also add the , operator to the end to remove newlines. | ``WRT,hello world,``|
| ``SET``   | Save a variable          | ``SET,MY_VAR_NAME,1``|
| ``STK``   | Create a new stack to place commands in | ``STK``|
| ``END``   | Stop the program with return code (integer) | ``END,0`` |
| ``ESC``   | Escape from a while loop manually | ``ESC`` |
| ``IF``    | If statement | ``IF,$VAR1,$VAR2`` |
| ``WHILE``    | While loop | ``WHILE,$VAR1,$VAR2`` |

## Symbols
Symbols.
| Symbols   | Description             | Example   |
|-----------|-------------------------|-----------|
| ``,``   | Seperates values in arguments (commands + statements) | ``SET,MY_VAR_NAME,1``|
| ``<<<``   | Intake symbol. Asks the user for a value. | ``SET,TEST,<<`` |
| ``+++``  | The "true" symbol. Useful for loops because it always returns true. | ``?,+++`` |
| ``---``  | The "false" symbol. Useful for loops because it always returns false. | ``?,---`` |
| ``$``    | Get the value of a variable | ``$VAR_NAME`` |
