# Scala Cheat Sheet
## Scala as a langage
Scala is a hybrid functional programming language. Scala integrates the features of object-oriented and functional languages. Scala is compiled to run on the Java Virtual Machine.

### Scala is object-oriented
Scala is a pure object-oriented language in the sense that every value is an object. Types and behavior of objects are described by classes and traits.

### Scala is functional
Scala is also a functional language in the sense that every function is a value and every value is an object so ultimately every function is an object.

### Scala is statically typed
Scala does not expect you redundant type information. You don't have to specify a type in most cases, and you certainly don't have to repeat it.

### Scala runs on the JVM
Scala is compiled into Java Bytecode which is executed by the Java Virtual Machine (JVM). This means that Scala and Java have a common runtime platform.

### Scala can Execute Java Code
Scala enables using all the classes of the Java SDK and custom Java classes, or Java open source projects.

### Scala can do Concurrent & Synchronize processing
Scala allows expressing general programming patterns in an effective way. It reduces the number of lines and helps the programmer to code in a type-safe way. It allows writing codes in an immutable manner, which makes it easy to apply concurrency and parallelism (Synchronize).

### Java Vs. Scala
* Unlike Java, Scala is a pure object-oriented language in the sense that every value is an object.
* Scala adopts type interference notion: types definition is not required upon variable declaration. 
* Java doesn't have immotable variables.
* Scala's syntax is much lighter : multiple java lignes could be reduced to one instruction in scala.  
* Scala has lazy evaluation (will be explained later).
* Scala supports operator overloading.
* Scala enables functional programming (Java 8 implements some aspects of functional programming, however scala provides almost every functional programming aspect).

### Higher order functions
A function that takes a function as an argument, or returns a function.

## Scala syntax notions
### What is « val » ?
val is used to declare immutable variables: it cannot be re-affected. It has to be initiated upon declaration. 

### « val » Vs. « var »
var is used to declare mutable variables and val is used to declare immutable variables. 

### What is «Lazy» ?
A val executed when it is defined whereas a lazy val is executed when it is accessed the first time.

### What are «Companion Objects» ?
Scala classes cannot have static variables or methods. Instead they can have singleton objects. When a singleton object is named the same as a class, it is called a companion object. A companion object must be defined inside the same source file as the class.

