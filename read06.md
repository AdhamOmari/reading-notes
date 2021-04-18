-[read01](read01.md)
-[read02](read02.md)
-[read03](read03.md)
-[read04a](read04a.md)
-[read04b](read04b.md)
-[read05](read05.md)
-[read06](read06.md)


# JavaScript & jQuery


## WHAT IS A FUNCTION? 

**
 Functions let you group a series of statements together to perform aspecific task. If different parts of a script repeat the same task, you canreuse the function (rather than repeating the same set of statements). **

__java Script example __
 >var x = myFunction(4, 3);   // Function is called, return value will end up in x
 function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}

Declaring A FUNCTION
==============
![img](https://cdn.programiz.com/cdn/farfuture/b4h4Zo5ZYxj-EyfQyao-J5TqbKEefFgqqusPGLWPFS0/mtime:1591786573/sites/tutorial2program/files/javascript-return-statement.png)



### return value

Let’s start with creating a simple multiply function in Vanilla JavaScript.
-------------------

*- function getMultiply(numberParam) {
   console.log('Multiply', numberParam * numberParam);
}
So now this function will multiply the number 7. But we can’t do anything with the outcome of it.
Return a value from the function
Let’s bring in the return statement.

function getMultiply(numberParam) {
   return numberParam * numberParam;
}
Now we have to call the function in the console.log to see the outcome.
console.log(getMultiply(7));
If we put this function into a variable, we have the outcome stored inside of it!
With the return statement, you can put anything out of the function.
If you want to return true, false or an Object or Array.-*


![img](https://www.tutsmake.com/wp-content/uploads/2020/05/JavaScript-Anonymous-Functions.jpeg)
