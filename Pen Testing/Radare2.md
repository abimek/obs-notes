# Radare2
#command #debugger #linux
Date: 08-04-2022

Radare2 is a complete framework for reverse-engineering and analyzing binaries; composed of a set of small utilities that can be used together or independently from the command line.

**Command:**  
``r2 || radare2``
**Flags**
```
# Run it in debugging mode
-d
```
**External Links:**
[Wiki](https://r2wiki.readthedocs.io/en/latest/)
[Intro](https://github.com/radareorg/radare2/blob/master/doc/intro.md)

```ad-info
title: tips
* run **aaa** before anything else to analyze the file
```

## Views

* **HexDump:** The hex dump shows the hex values of the binary
* **Disassembler:** Disassembled binary
* **Debugger:** When debuging takes place

## Commmands
```
# Run shell commands
!<command>

# Analyze Binary
aaa

# Lists functions
afl

# Open up initial view
V

# Go to next view
p

# Go back one view
P

# Seeks out a function or memory address in the view 
s

# Go back to current view when on a child view/menu
u

```

## Debuggin

```
# Open up the control flow visualizer
VV

# Number of lines on the debugging stack
e stack.size = <lines_wanted*16>

# Step through an instruction
f7

# Set a debugging break point
db <place>

# continue execution until breakpoint or completion
dc

```