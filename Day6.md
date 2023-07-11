# Day 6: JavaScript Principles and Functions & Callbacks
The following README file provides a brief overview of the JavaScript lessons on JavaScript Principles, Functions & Callbacks. These lessons cover the implementation of JavaScript principles, explore functions, and emphasize the importance of callbacks. They offer a comprehensive understanding of JavaScript fundamentals, efficient function usage, and the significance of callbacks in code execution.

## Lesson 1: << JavaScript Principles >>

In this lesson we've been introduced to some of JavaScript features and some of  the general programming principles. key points covered in this lesson are:

- JavaScript Features: as a programming language JavaScript has a thread of excution which is linear (goes line by line and excutes each line), also JavaScript gives us the ability to store variables and functions (which are some lines of code) in memory to use them later on in our program.
- Functions: code we save and we can later one invoke to make use of, which increases reusability.
- Excution Context: it's more like an enviroment that has memory which the excution of the program happens in. There are 2 types of excution contexts:
  Global Execution Context (GEC): Is an important concept in JavaScript that represents the environment in which global JavaScript code is executed. It is created when a JavaScript program starts running and serves as the foundation for the entire code execution process.
  The Function Execution Context (FEC) Is a concept in JavaScript that represents the environment in which a function is executed. It is created whenever a function is invoked and exists for the duration of the function's execution.
* it is worth to mention that both GEC & FEC have seperate temporarily excution memroy to save variables and functions.

- As soon as we start any function, we create a mini excution context called the function excution context.
- JavaScript can do one thing at a time, which means that we only have one thread of excution.
- There is a way that lets JavaScript know where is the current thread of excution is happening, which is the Call Stack.
  Call stack is a way of helping javascript to know where the thread of excution is currently at (globally or inside a function).
  so if the call stack is empty that means we're running globally.
- After a function terminates it is removed off the stack so is its local memroy.

## Lesson 2: << Functions & Callbacks >> 
In that lesson we've been introduced to functions and what happens behind-the-hood. here are the main points covered:

- A common mistake that must be avoided is "DRY" which is a short term to "Dont repeat yourself" which is a funcdemental general programming principle.
- functions that return the same output are boring functions, a more generalized function is a state that we want to lay our hands on, also generalized functions increase reusability and makes the code more dynamic.
- functions that are similar in functionality are acutlly not considered as fully generalized functions, there is always a better solution, an good example of that would be the functions that were provided to do some functionality which are addtion,mutliplication,subtraction and division.
so one solution for such thing, is to define 4 dynamic functions that take input and act accordingly, and send them as a instruction parameter to the general function to provide reusablility.
- Functions can be treated like objects.
  this means that functions can be assigned to variables can can be passed to other functions as arguments.

- a higher order function is any function that takes in or returns out a function is a higher order function
Anonymous and arrow functions
- Arrow functions increase immediate legibility of the code.

## Coding Examples

### < JavaScript Principles >

```javascript
const num = 3;
function addThree(Num) {
const result = Num+3;
return result;
}
const output = addThree(4);
console.log(output); //this will output 3;

//An example of repeated code.
function tenSquared() {
const result = 10*10;
return result;
}
function nineSquared() {
const result = 9*9;
return result;
}

//A better function
function square(num) {
const result = num*num;
return result;
}
```
### < Functions & Callbacks >
```javascript
//bad way to write funcntions.
function copyArrayAndManipulate(arr) {
const output = []
  for(let o = 0; o <arr.length;o++) {
      output.push(arr[o]/2); // just one operation per function, bad code!
}
return output;
}


function copyArrayAndManipulate(arr,instruction) {
const output = []
  for(let o = 0; o <arr.length;o++) {
      output.push(instruction(arr[o])); // given operation, as many operations as we wish to make.
}
return output;
}
function multilplyBy2(num) {return num*2;} // we can add more functions to perform other operations as well.
const result = copArrayAndManipulate([1,2,3,4],multiplyBy2);

//same functioon but written as an arrow function

function copyArrayAndManipulate(arr) {
const output = []
  for(let o = 0; o <arr.length;o++) {
      output.push(instruction(arr[o]));
}
return output;
}
const result = copArrayAndManipulate([1,2,3,4],num=>num*2);
```
### Coding exercises provided by the GSG Team
[Excercise: Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
```javascript
const squareList = arr => {
  // Only change code below this line
  const newarr = arr.filter(iterator=>Math.ceil(iterator) === iterator && iterator >=0);
  return newarr.map(iterator=> iterator*iterator);
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

[Exercise: Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

```javascript
// Only change code below this line
function urlSlug(title) {
  const arr = title.split(" ");
 const temparr =  arr.map(iterator=>iterator.toLowerCase())
  const newarr = temparr.filter(iterator=>iterator.length)
  return newarr.join("-").trim();
}
// Only change code above this line
urlSlug("         Winter Is        Coming")
```
Problem Statement:
Implement a JavaScript function called mapAsync that takes an array and a callback function. The function should map each element of the array to a new value using the callback function asynchronously.

The final result should be returned as a Promise.

My solution:
```javascript
function mapAsync(arr, callback) {
    let promises = arr.map((el) => {
      return new Promise((resolve, reject) => {
        try {
          resolve(callback(element));
        } catch (error) {
          reject(error);
        }
      });
    });
    return Promise.all(promises);
  }
  let arr = [1,2,3,4,5];

  mapAsync(arr,el=>el+3).then(resolved=> console.log(resolved)).catch(err=>console.log(err));
```

Problem Statement:
Write a JavaScript function called sumRange that calculates the sum of all integers in a given range. The function should use recursion to handle the calculation and demonstrate understanding of the call stack.

My solution:
```javascript
function sumRange(start,end) {
    if(start > end)
        throw new Error("Start point must be less than or equal starting point.")
    else if(start === end)
        return start;
    else 
        return start+sumRange(start+1,end);
}
try{
    console.log(1,2); // will output 3;   
}
catch(err) {
    console.log(err);
}
```
