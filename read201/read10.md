# JavaScript can be hard to learn and everyone makes 
>mistakes when writing it. This chapter will help you learn 
how to find the errors in your code. It will also teach you how 
to write scripts that deal with potential errors gracefully. 

- THE CONSOLE & 
DEV TOOLS 
Tools built into the browser 
that help you hunt for errors
- COMMON 
PROBLEMS 
Common sources of errors, 
and how to solve them. 
- HANDLING 
ERRORS 
How code can deal with 
potential errors gracefully

> The JavaScript interpreter uses the concept of execution contexts. 
There is one global execution context; plus, each function creates a new 
new execution context. They correspond to variable scope

----------------
###### EXECUTION CONTEXT 
> *Every statement in a script lives in one of three 
execution contexts:*

1. >GLOBAL CONTEXT 
Code that is in the script, but not in a function. 
There is only one global context in any page.
FUNCTION CONTEXT 
Code that is being run within a function. 
Each function has its own function context.
2. EVAL CONTEXT (NOT SHOWN) 
Text is executed like code in an internal function 
called eva l {) (which is not covered in this book). 
3. >GLOBAL SCOPE 
If a variable is declared outside a function, it can 
be used anywhere because it has global scope. 
If you do not use the var keyword when creating 
a variable, it is placed in global scope.
GLOBAL SCOPE 
If a variable is declared outside a function, it can 
be used anywhere because it has global scope. 
If you do not use the var keyword when creating 
a variable, it is placed in global scope.

---------------------
 ![alt](https://th.bing.com/th/id/OIP.SPrbWhDOBUwLpkqusaITCAHaEC?w=278&h=180&c=7&o=5&pid=1.7)


---------------
##### UNDERSTANDING SCOPE
>In the interpreter, each execution context has its own va ri ables object. 
It holds the variables, functions, and parameters available within it. 
Each execution context can also access its parent's v a ri ables object.


---------------------

----------

###### UNDERSTANDING ERRORS 
> **If a JavaScript statement generates an error, then it throws an exception. 
At that point, the interpreter stops and looks for exception-handl ing code.**


###### ERROR OBJECTS 

>*Error objects can help you find where your mistakes are 
and browsers have tools to help you read them. *
![alt](https://th.bing.com/th/id/R903db5757c63d7aafebeaa1896aeb925?rik=FWobhFIDBWjuSw&pid=ImgRaw)

------------
