# pdb debugger

Debug python in the terminal with `pdb`.

>Note: get color version with `ipdb` (pip install ipdb)

Run the program for a given file
> python -m ipdb my_file.py
>> -m = mode

| key                | action                                     |
|--------------------|--------------------------------------------|
| l                  | list 11 lines around the current line      |
| s (number of step) | step                                       |
| c                  | continue until error/breakpoint            |
| r                  | continue until the current function return |
| b [line nbr]       | create a break point                       |
| p [variable]       | print a variable                           |
| restart            | restart the program                        |
| q                  | quit the debugger                          |
