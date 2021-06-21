## Lists and Keys
###### What does .map() return?

> `map()` function returns a map object(which is an iterator) of the results after applying the given function to each item of a given iterable (list, tuple etc.) ... 
>  : It is a function to which map passes each element of given iterable. iter : It is a iterable which is to be mapped.

> > *If I want to loop through an array and display each value in JSX, how do I do that in React?*
> we loop through the numbers array using the JavaScript map() function. **using  `{}`**

> **Each list item needs a unique ____.** 
- Keys should be unique among their siblings

> What is the purpose of a key?
  *Keys help React identify which items have changed, are added, or are removed.*
  -------------------------------

  ### Use the Spread Operator
  > What is the spread operator?

* The spread operator is a new addition to the set of operators in JavaScript ES6. It takes in an iterable (e.g an array) and expands it into individual elements. The spread operator is commonly used to make shallow copies of JS objects. Using this operator makes the code concise and enhances its readability.

> List 4 things that the spread operator can do.?
>1. Copying an array.
> 2. Concatenating or combining arrays.
> 3. Using Math functions.
> 4. Using an array as arguments.
> 5. Adding an item to a list.
> 6. Adding to state in React.
> 7. Combining objects.
> 8. Converting NodeList to an array.

------------------
> Give an example of using the spread operator to combine two arrays.
>
` const cars = ['🚗', '🚙'];
const trucks = ['🚚', '🚛'];

const combined = cars.concat(trucks);
// [ '🚗', '🚙', '🚚', '🚛' ]

console.log(cars); // ['🚗', '🚙'];
console.log(trucks); // ['🚚', '🚛'];`

-----------------
> Give an example of using the spread operator to add a new item to an array.

> `function sum(x, y, z) {
  return x + y + z;
}

const numbers = [1, 2, 3];

console.log(sum(...numbers));
// expected output: 6

console.log(sum.apply(null, numbers));
// expected output: 6`

-----------------------------

> Give an example of using the spread operator to combine two objects into one. ? 

`let person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    ssn: '123-456-2356'
};


let job = {
    jobTitle: 'JavaScript Developer',
    location: 'USA'
};

let employee = {
    ...person,
    ...job
};

console.log(employee);`