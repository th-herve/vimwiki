# Basic Guide to Debugging with GDB

Debugging with GDB (GNU Debugger) is an essential tool for finding and fixing errors in your code. Here's a basic guide to help you get started:

## Compiling and Running the Program

1. Compile with debugging information: `gcc -g -o program program.c`
2. Start gdb with the program: `gdb program`
3. Set a breakpoint: `break [function/line number]`
4. Run the program: `run [arguments]`

## Controlling Program Flow

- `break [function/line number]`: Set a breakpoint at the specified function or line number.
- `delete [optional number]`: Delete all breakpoints or just the optional number one.
- `continue`: Continue running the program until the next breakpoint is hit or the program exits.
- `next`: Execute the current line and move to the next line in the source code, without stepping into function calls.
- `step`: Execute the current line and step into any function calls on that line.
- `until [optional line]`: Run the program until it reaches the specified line or until the current function returns.

## Information Commands

- `info breakpoints`: List all breakpoints.
- `info functions`: List all functions in the program.
- `info variables`: List all global variables in the program.
- `info locals`: List all local variables in the current function.
- `backtrace`: Show the current call stack.
- `info [args]`: Display various types of information, such as info breakpoints, info functions, info locals, and more.

## Data Manipulation

- `print [expression]`: Evaluate the specified expression and print its value.
- `set [variable]=[value]`: Change the value of the specified variable.
- `display [expression]`: Print the value of the specified expression every time gdb stops.

## Miscellaneous Commands

- `list [optional line]`: Show 10 lines of the code starting at the optional line (also works with list 1,10 to list lines 1 through 10).
- `watch [expression]`: Set a watchpoint on the specified expression, so that gdb will break whenever that expression is modified.
- `finish`: Run the program until the current function returns.
- `set print pretty on`: Enable pretty-printing for complex data structures.
- `set print elements [number]`: Set the number of elements gdb will print when displaying arrays and structures.
- `set follow-fork-mode [parent/child]`: Set the follow-fork-mode for debugging forked processes.
- `set detach-on-fork [on/off]`: Set whether gdb will automatically detach from forked processes.
- `set pagination [on/off]`: Set whether gdb will pause after displaying a full screen of output.

To quit gdb, simply type `quit`. 
