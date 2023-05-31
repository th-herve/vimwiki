# C# basics

## Basic input/output

```C#
Console.WriteLine("Enter your name: "); 
 
name = Console.ReadLine();
```

## Comment 

```C#
// This is a single line comment

/* This is a multi-line comment
   and continues until the end */
```

## Logical operato
* &&
* ||
* !

## Comparison operator
* ==
* !=
* \> 
* \>=
* <  
* <=
<br><br>
# Control flow

## if statements

```C#
if (true)
{

}

else if (false)
{

}

else
{

}
```
## Switch

```C#
switch (variable)
{
   case "1":
      // code
      break;

    case "2":
      // code
      break;

   default:
      // code
      break;
}
```

## For loop
- for (initialisation; stopping condition; iteration statement)
```C#
for (int i = 0; i < 10; i++)
{

}
```

## For each loop
- run x time the number of element in a given collection
- initiate a variable with each loop

```C#

string[] states = { "Alabama", "Alaska", "Arizona", "Arkansas", "California", "Colorado" };

foreach (string state in states) {
  Console.WriteLine(state);
}
```

## While loop
```C#
int x = 0;
while (x < 3)
{
   x ++;
}
```

## Do while loop
- like a while loop but garantee one iteration even if condition false
```C#
int x = 0;
do 
{
   x ++;
} while (x < 3);
```

## Jump statement 
- break
- continue
- return

```C#
while (true) {
  Console.WriteLine("This prints once.");
  // A `break` statement immediately terminates the loop that contains it.
  break;
}

for (int i = 1; i <= 10; i++) {
  // This prints every number from 1 to 10 except for 7.
  if (i == 7) {
    // A `continue` statement skips the rest of the loop and starts another iteration from the start.
    continue;
  }
  Console.WriteLine(i);
}

static int WeirdReturnOne() {
  while (true) {
    // Since `return` exits the method, the loop is also terminated. Control returns to the method's caller.
    return 1;
  }
}
```

## Ternary Operator
condidtion ? expression true : expression false;
if condition true, return expression 1 else expression 2
```C#
string ternary = isRaining ? "Umbrella" : "No Umbrella";
```

<br><br>

# Variable and types

| Data Type | Description             | Memory Size  |
|-----------|-------------------------|--------------|
| `bool`    | Boolean                 | 1 byte       |
| `byte`    | Byte                    | 1 byte       |
| `sbyte`   | Short Byte              | 1 byte       |
| `char`    | Character               | 2 bytes      |
| `decimal` | Decimal                 | 16 bytes     |
| `double`  | Double                  | 8 bytes      |
| `float`   | Float                   | 4 bytes      |
| `int`     | Integer                 | 4 bytes      |
| `uint`    | Unsigned Integer        | 4 bytes      |
| `nint`    | Native Integer          | 4 or 8 bytes |
| `unint`   | Unsigned Native Integer | 4 or 8 bytes |
| `long`    | Long                    | 8 bytes      |
| `ulong`   | Unsigned Long           | 8 bytes      |
| `short`   | Short                   | 2 bytes      |
| `ushort`  | Unsigned Short          | 2 bytes      |

## Declaration

```csharp
bool isOpen = true;
byte age = 45;
sbyte temperature = 58;
char grade = 'a';
decimal numberOfAtoms = 1493867940.23m;
double weightOfHippos = 243906.12;
float heightOfGiraffe = 908.32f;
int seaLevel = -24;
uint year = 2023u;
nint pagesInBook = 412;
unint milesToNewYork = 2597;
long circumferenceOfEarth = 25000l;
ulong depthOfOcean = 28000ul;
short tableHeight = 4;
ushort treeBranches = 33;
```

### Array

```csharp
// if initialisation 
int[] arrayName = new int[] {1, 2, 3};
// or
int [] arrayName = {1, 2, 3}

// no initialisation
int[] arrayName = new int[5]

myIntArray[0] = 1; 
```


### List

In C#, a list is a dynamic array that can grow or shrink in size.

```csharp
// declaration
List<int> myIntList = new List<int>();
// or 
List<int> myIntList = new List<int>() {1, 2, 3};

myIntList.Add(1);

int firstElement = myIntList[0];

int count = myIntList.Count; // Get the count of elements in the list

myIntList.Remove(2); 

bool containsElement = myIntList.Contains(3);
```

## Enum

In C#, an enum (short for "enumeration") is a set of named constants that represent distinct values of a particular type. Enums are used to define a set of values that are meaningful and represent a discrete set of options or states. 

```csharp
enum DaysOfWeek
{
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}

DaysOfWeek today = DaysOfWeek.Monday; // Declare and initialize a variable with an enum value

if (today == DaysOfWeek.Monday)
{
    Console.WriteLine("Today is Monday"); // Check the value of the enum variable
}
```
