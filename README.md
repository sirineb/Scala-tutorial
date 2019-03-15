# Scala Cheat Sheet
## Scala as a language
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
* Java doesn't have immutable variables.
* Scala's syntax is much lighter : multiple java lignes could be reduced to one instruction in scala.  
* Scala has lazy evaluation (will be explained later).
* Scala supports operator overloading.
* Scala enables functional programming (Java 8 implements some aspects of functional programming, however scala provides almost every functional programming aspect).

### Higher order functions
A function that takes a function as an argument, or returns a function.

## Scala syntax notions
### val
val is used to declare immutable variables: it cannot be re-affected. It has to be initiated upon declaration. 

### « val » Vs. « var »
var is used to declare mutable variables and val is used to declare immutable variables. 

### lazy
A val executed when it is defined whereas a lazy val is executed when it is accessed the first time.

### Companion Objects
Scala classes cannot have static variables or methods. Instead they can have singleton objects. When a singleton object is named the same as a class, it is called a companion object. A companion object must be defined inside the same source file as the class.

```
class Main {
        def sayHelloWorld() {
                println("Hello World") }}
object Main {
        def sayHi() {
                println("Hi!") }}
var aMain : Main = new Main()
aMain.sayHelloWorld()
Main.sayHi()
```

### «class» Vs. «case class» 
A case class is good for modeling immutable data. It is useful for pattern matching. It has a default apply() method that handles object construction.
* We can create an instance of `case class` without the keyword `new`.
* Parameters used when creating a case class are transformed automaticly into public attributes.
* case class re-implements the method `equals` automatically: two instances with the same parameters are equal. 
* A case class cannot inherit a case class. 

### sealed class 
sealed class can only be inherited if the child class is defined in the same source file. 

### For-Comprehension
Comprehensions have the form for (enumerators) yield e, where enumerators refer to a semicolon-separated list of enumerators. An enumerator is either a generator which introduces new variables, or a filter. The for loop used with a yield statement actually creates a List. 
```
case class User(name: String, age: Int)
val userBase = List(User("Travis", 28), User("Kelly", 33), User("Jennifer", 44))
val twentySomethings = for (user <- userBase if (user.age >=20 && user.age < 30))
yield user.name 
```
### implicit 
It helps solve type ambiguity or non declared parameters. There are two types of implicit: 
* implicit parameters: considering a function that has the keyword “implicit” placed before its arguments. When such a function is called without initiating its arguments, the uninitiated arguments will be replaced with implicit variables declared in the class or in companion objects where the function was declared. 
* implicit conversions: a function X with one argument of type A, and a implicit function Y with one argument of type B and returns a value of type A. X could be called with an argument of type B. B will be transformed into type A using the function Y. The same principle goes for classes and their constructors. 

### Tail recursion
If the last action in a recursive function is a call to the function itself, the recursive function is a tail recursion. A simple recursion allocates as many memory units as the recursions. However, Scala detects tail recursion and allocates one memory unit. The function is annotated with @tailrec. The code won’t compile if the function defined is not a tail recursion to start with. 

### « map » Vs. « flatmap »
map returns a collection of the same size as the input collection. flatMap is a combination between map and flatten: it allows returning a collection larger or smaller that the input collection elle permet de retourner une collection plus ou moins large que la collection d’entrée.

### Creating an interface in scala
Scala doesn’t have interfaces, however traits could replace them. Traits have functions signatures only.

### Type inference 
It’s a mechanism allowing to detect types of variables or expressions or functions without explicitly declared. 

### Null in Scala
null is an object in scala. It is preferable to avoid using it. If a program uses a java method returning a null it is recommended to transform it into Option.  

### Function concepts
* A call-by-name mechanism passes a code block to the call.
* Named arguments allow passing arguments to a function in a different order.
* Variable arguments functions allow indicating that the last parameter to a function may be repeated.
```
def printStrings( args:String* ) = {
        var i : Int = 0
        for( arg <- args ){
                println("Arg value[" + i + "] = " + arg )
                 i = i + 1}}
```
* Scala allows specifying default values for function parameters. 
* Higher order functions take other functions as parameters, or whose result is a function.
* Nested functions: Scala allows defining functions inside a function. 
* Anonymous functions in source code are called function literals.
```
var inc = (x:Int) => x+1
println(inc(7))
```
* Currying transforms a function that takes multiple parameters into a chain of functions, each taking a single parameter.
