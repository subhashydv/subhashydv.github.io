---
title: "Kotlin"
date: 2024-05-01T17:33:51+05:30
draft: false

tags: 
  - Tech
  - Tutorial
  - Programming language

categories: ["Tech", "Tutorial", "Kotlin"]

description: A Programming language
thumbnail: "/images/Kotlin.jpeg"
image: "/images/Kotlin.jpeg"
---

## About Kotlin : 

Kotlin is a programming language, that runs on Java Virtual Machines (JVMs) and that can also be compiled to JavaScript. This programming language is statically typed, which means that variables, functions, and expressions use predefined sets of types that can be checked on compile time.

## How kotlin is different from java

Java and Kotlin both are widely used programming languages, but there are some differences. Lets see these difference : 

### Syntax :
One of the most significant differences between all programming language would be the syntax. Kotlin has a more precise syntax than Java, which means that it requires less code to perform the same actions. 
let's see the syntax by declaring a variable : 

 ```
 // kotlin
 val greet = "Good morning"
 ```

 here we can see that kotlin supports type inference, which means that you do not have to specify the data type of a variable explicitly.

 ```
 // java
String greet = "Good morning"
```
where in java, you need to specify the data type of the variable which can make your code more verbose.

similarly for class we don't need to explicitly add getter and setters for fields

```
// kotlin

class Person(private val name: String) {
   fun getName() = name
   fun setName(value: String) { name = value }
}
```
in Java we create a class as follows : 

```
// java

public class Person {
   private String name;

   public Person(String name) {
      this.name = name;
   }

   public String getName() {
      return name;
   }

   public void setName(String name) {
      this.name = name;
   }
}
```
Similarly We have many more differences in syntax of kotlin and java.

### Null Safety :
Null safety is another area where Kotlin differs from Java. In Java, it's possible to have null values assigned to a variable, which can lead to null pointer exceptions at runtime. Kotlin, on the other hand, requires you to explicitly define whether a variable can be null or not. This makes it easier to avoid null pointer exceptions during runtime.

For example, in Kotlin, all variables are non-null by default, meaning that they cannot hold a null value unless explicitly declared as nullable using the "?" operator. This helps to prevent null-related errors at compile-time, rather than waiting until runtime.

```
// kotlin

var name: String = "Chris" // non-null variable

var age: Int? = null // nullable variable
```

In Java we need handling for null pointer, where in kotlin we already know which variable can store the null values.

### Data Class :
In kotlin data classes are designed to hold the data. For a data class complier automatically generates few additional function that helps to compare instance, copy instances, print the data and more.
The syntax for the data class is as following : 

```
data class Person(
      val name: String, 
      val age: Int
    )
```

Data classes may extend other classes. for example sealed classes


### Functional Programming Features :
Other major difference between Java and Kotlin is their support for functional programming. While Java has added support for functional programming with Java 8, Kotlin was designed from the start to support functional programming.

For example, Kotlin supports lambda expressions, higher-order functions, and extension functions.
These features make it easier to write code that is both concise and expressive. Here is a code sample showing this:

**Lambda Expression**

```
val list = listOf("hi", "hello", "bye")
val sizeOfList = list.map { it.length }
```

**extension function**

```
fun Int.isOdd() = this % 2 == 1
val isFiveOdd = 5.isOdd()
```

**higher-order function**

```
fun higherOrderFunc(x: Int, y: Int, f: (Int, Int) -> Int): Int {
    return f(x, y)
}
val result = higherOrderFunc(3, 4) { x, y -> x * y }
```

*Here is another example for higher order function :*

```
fun add(number1:Int): (Int) -> Int {
    return { number2: Int -> number1 + number2 }
}

val addTwo = add(2)
val sum = addTwo(3)
```

This was an small overview of kotlin. If you want to learn more about kotlin then visit their official documentation [page](https://kotlinlang.org/docs/home.html)

*Hope this information was helpful :)*