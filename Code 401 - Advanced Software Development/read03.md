# Java Primitives versus Objects

> Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a reference type.

>Every object contains a single value of the corresponding primitive type. The wrapper classes are immutable (so that their state can't change once the object is constructed) and are final (so that we can't inherit from them).

> Under the hood, Java performs a conversion between the primitive and reference types if an actual type is different from the declared one:
> 
`Integer j = 1;          // autoboxing
int i = new Integer(1); // unboxing`



> The decision what object is to be used is based on what application performance we try to achieve, how much available memory we have, the amount of available memory and what default values we should

###### Just for the reference, the primitive type variables have the following impact on the memory:

* boolean – 1 bit
* byte – 8 bits
* short, char – 16 bits
* int, float – 32 bits
* long, double – 64 bits

![alt](https://www.researchgate.net/profile/Sven-Otto-3/publication/339737384/figure/tbl1/AS:865931035172876@1583465455572/Asymptotic-critical-values-for-the-retrospective-tests_Q320.jpg)
> In practice, these values can vary depending on the Virtual Machine implementation. In Oracle's VM, the boolean type, for example, is mapped to int values 0 and 1, so it takes 32 bits, as described here: Primitive Types and Values.

> Variables of these types live in the stack and hence are accessed fast. For the details, we recommend our tutorial on the Java memory model.


> The situation becomes more interesting if we compare how much memory occupy arrays of the types under consideration.


> What Is an Exception?
**Definition: An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions.**

> After a method throws an exception, the runtime system attempts to find something to handle it. The set of possible "somethings" to handle the exception is the ordered list of methods that had been called to get to the method where the error occurred. The list of methods is known as the call stack (see the next figure).

![alt](https://docs.oracle.com/javase/tutorial/figures/essential/exceptions-callstack.gif)
> The call stack showing three method calls, where the first method called has the exception handler.

> Valid Java programming language code must honor the Catch or Specify Requirement. This means that code that might throw certain exceptions must be enclosed by either of the following:

> The Catch or Specify Requirement

> A try statement that catches the exception. The try must provide a handler for the exception
> A method that specifies that it can throw the exception. The method must provide a throws clause that lists the exception, 

> A program can use exceptions to indicate that an error occurred. To throw an exception, use the throw statement and provide it with an exception object — a descendant of Throwable — to provide information about the specific error that occurred. A method that throws an uncaught, checked exception must include a throws clause in its declaration.

 > A program can catch exceptions by using a combination of the try, catch, and finally blocks.

> The try block identifies a block of code in which an exception can occur.
The catch block identifies a block of code, known as an exception handler, that can handle a particular type of exception.

> The finally block identifies a block of code that is guaranteed to execute, and is the right place to close files, recover resources, and otherwise clean up after the code enclosed in the try block.
The try statement should contain at least one catch block or a finally block and may have multiple catch blocks.

> The class of the exception object indicates the type of exception thrown. The exception object can contain further information about the error, including an error message. With exception chaining, an exception can point to the exception that caused it, which can in turn point to the exception that caused it, and so on.

*Scanning*

*Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.*

`import java.io.*;
import java.util.Scanner;

public class ScanXan {
    public static void main(String[] args) throws IOException {

        Scanner s = null;

        try {
            s = new Scanner(new BufferedReader(new FileReader("xanadu.txt")));

            while (s.hasNext()) {
                System.out.println(s.next());
            }
        } finally {
            if (s != null) {
                s.close();
            }
        }
    }
}`