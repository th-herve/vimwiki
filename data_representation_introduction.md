# === Data representation intro ===


## Bytes of memory

Pc memory is a huge array of bytes (number between 0 and 255 or 8 bits). Each slot is identified by an address.  
A bit is the smallest unit of storage and hold 0 or 1. More complicated object are represented by a collection of bits.

## Object

C++ programs construct, examine and modify `objects`. An object is a contiguous region of data storage that contain a value.  
Object `never overlaps`.

## Segment

Each object has a lifetime or storage duration. 3 different kind:

    1. static lifetime: object last as long as the program run (ex: global variable)
    2. automatic lifetime: compiler allocates and destroy the object based on his scope (ex: local variable)
    3. dynamic lifetime: the programmer allocates and destroys the object `explicitly`
     
Dynamic lifetime object can cause serious problem, such as memory leaks, double-free...  
But they have advantages such as construct object whose size is unknown at compile time, or object that outlives the function that created it.

The compiler and os work together to put object at  different address. A program address space are divided into region called `segment`.  
The lifetime of an object determine which segment it's put in.

The most important segments are:

    | segment | contain                                | type                           |
    |---------|----------------------------------------|--------------------------------|
    | Code    | instruction and constant global object | Unmodifiable, static lifetime  |
    | Data    | Non constant global object             | Modifiable, static lifetime    |
    | Heap    |                                        | Modifiable, dynamic lifetime   |
    | Stack   |                                        | Modifiable, automatic lifetime |
    
> the compiler decide on a segment for each object based on its lifetime. The `linker` group the object by segment. When running, the os load the segment into memory.


## Unsigned integer representation

C++ manage memories in unit of bytes (8 contiguous bits) that can represent number from 0 to 255.  
To represent bigger number (ex: 258), the computer use multiple bytes. Modern pc uses `place-value notation`. The number is determine by its digit and their places in the overhaul number.  
Pc uses a base 256 instead of 10.  
Ex: 258 = 1 * 256¹ + 2 * 256⁰
or
256 = | 2 | 1 | (where each case is a bytes, note that the first digit is on the left or `little-endian` notation)

Step to represent a multi-byte integer in memory, let's store a 65534 unsigned int as example:

    1. write the number in hexa, including all leading 0 required by the type size(unsigned is 4 bytes) so 65534 would be writeen 0x0000FFFE
    2. break it down into each byte: 0x00, 0x00, 0xFF, 0xFE
    3. in little-endian, each byte are stored starting from the least significant. If the number 65534 was stored at address 0x30, that gives us:
        0x30: 0xFE    0x31: 0xFF    0x32: 0x00    0x33: 0x00
    > the trailing 0 are necessary in this example because of the size of a unsigned int, we would get rid of them if the type was unsigned short (only 2 bytes so 0xFFFE)



| function             | action                      | library  |
|----------------------|-----------------------------|----------|
| std::cout << "text"  | output character on console | iostream |
| std::cin >> variable | read input from console     | iostream |
|                      |                             |          |
