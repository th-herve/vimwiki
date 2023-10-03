# Java override toString

Inside a class definition, the toString method is often override. By default
it print the data type of the object followed by the memory address. Overriding it allow to give it a more meaningful output.

```java
public class Cat {
    String name = "Felix";
    int numLives = 9;
    
    @override   // not necessary
    public String toString() {
        return  this.name + " " + this.numLives;
    }
}
```
