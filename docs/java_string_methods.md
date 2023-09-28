# String methods

[full list](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html)

## .length()

```java
String str1 = "hello";
str1.length()
```

## .concat()

Return a new string

```java
String str1 = "hello";
newStr = str1.concat(" world!")
```

## .equals()

String behing an object, the `==` operator does not work.

```java
String str1 = "foo";
String str2 = "bar";
boolean test = str1.equals(str2);
```

> there is also `.equlsIgnoreCase()`

## .indexOf()

```java
String letters = "abcde";
letters.indexOf("c"); // 2
letters.indexOf("cde"); // 2
```

## .charAt()

```java
String str1 = "foo";
str1.charAt(2);
```

## .substring()

```java
String str1 = "abcde"
str1.substring(2); // index 2 to the end
str1.substring(0, 3); // index 0 to 2
```

## .toUpperCase() .toLowerCase()

```java
String str1 = "aBcD"
str2 = str1.toLowerCase()
str3 = str1.toUpperCase()
```
