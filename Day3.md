# Day 3: Quiz Project and Functions 
The following README file provides a concise overview of the JavaScript lessons covering the Quiz Project, Functions, and the usage of let and const scopes. Within these lessons, we delve into the process of constructing a quiz project using JavaScript, while also exploring the fundamental concepts and implementation of functions, as well as the utilization of let and const for variable scoping in JavaScript.

## Leeson 1: < Quiz Project > 

in this lesson we were asked to make a project which represents a yes-no answered quiz with the explanation for either answers.
we were specifically asked to use everything we've learned in JavaScript so far to do so.

For a more detailed understanding of the project, please continue reading.

- JavaScript Pop Quiz Overview: at first we had a concise overview of the JavaScript pop quiz. this quiz served as a test of our knowledge regarding the material covered thus far. Within this section, we explored the components of the quiz project, such as script tags and code comments and what they were used for.
- DOM exercise & Declaring and Assigning Variables: as mentioned this quiz serves as a test of our knowledge of the coverd topics earlier, this surely includes DOM, this task involved declaring variables such as `statement`, `optionButtons` and `explanation`, as well as creating the object which contains the information needed to be displayed and compared with user's choice.
- Setting Statement Element: This one involved changing the question displayed by accessing the HTML element which is assigned to `statement` variable and changing its content to the content that exists in fact.statement.



##Lesson 2: < Quiz Project Functions > 

### << Functions >>

so basically in this sublesson we delved into the world of funcions and their behaviour, here are the key points of what we've covered.

- Functions are essentially reusable blocks of code that can accept arguments, known as parameters, and perform operations involving these arguments. They may also optionally return values as results.
- Functions will always return a value, so there was no specific value to be returned the function will return an undefined value.
- there is a difference between arguments and parameters though, parameters are variables listed in the function's declaration whereas arguments refer to the actual values passed into a function when it is called.
- If you send fewer arguments than the number of parameters defined in a function, the missing parameters will have the value of `undefined`.
- Arrow Functions: is a new type of funcions that serves the same as the "normal" function but with less typing.
- When the function body consists of a single expression, the curly braces and the `return` keyword can be omitted.

### Code examples of << Funcions >>

``javascript
//An example of a normal function
function devide(a,b) { //begins with `function` keyword.
    return a/b; // returns a number
}

//Same example but implemeted as an arrow function
const devide = (a,b) => a/b; // returns the same output as the normal funcrion.

//undefined return value.
function devide(a,b) {
console.log(a/b); //outputs it
}
console.log(devide(1,2)); //outputs the number then "undefined".

//you can write a one paramertized arrow function as follows:
const newFunc = a => a*a; // will return the value of n*n.

//Arrow function with multiple statements.
const newFunc = a => {
conspole.log(a);
return a*a; // outputs a value and then returns a number of value n*n.
}

```

### << Scopes in JavaScript >>

Just as any programming language JavaScript has the concept of variable scopes, scopes actually define the limits where some variables are accessable.
JavaScript has two types of scopes: local and global. local scopes are defined within functions or specific blocks, which are enclosed by `{}`, while global scopes are not limited to any specific local area.

In ES6, the `let` keyword was introduced as an alternative to `var` for declaring variables. some of the key diffferences are covered as follows:

- Block scope: as mentioned the block scope is anything that lies inside two curly brackets `{}`, variables declared using the `let` keyword possess block scope, limiting their accessibility to the specific block of code where they are defined (enclosed within curly braces `{}`). anyhow, variables declared with `var` have either local scope or global scope.
- Redeclaration and Reassignment: Variables declared using the `let` keyword allow for reassignment to a new value, but they cannot be redecorated within the same block scope. though on the other hand, variables declared with `var` can be both reassigned and redecorated within the same scope.

### Code examples of << Scopes in JavaScript >>

```javascript

let str = "Global";

const newFunc = () => {
let str = "Local";
console.log(str); // outputs "Local"
}
console.log(str); //outputs "Global"

////////

{
let first = 83;
var second = 81;
console.log(first); // outputs 83
console.log(second) // outputs 81
}
console.log(first); // error
console.log(second) // outputs 81

```

### a code of the quiz project will be provided once completed.

## Coding Exercises provided by the GSG Team

### [Excercise: Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)

```javascript
const timesFive = (arg) => arg*5;
```

### [Exercise: Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)

```javascript
// Declare the myGlobal variable below this line
const myGlobal = 10;

function fun1() {
  // Assign 5 to oopsGlobal here
oopsGlobal = 5;
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```

### [Exercise: Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)

```javascript
function myLocalScope() {
  // Only change code below this line
let myVar;
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```

### [Exercise: Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)

```javascript
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  const outerWear = "sweater";
  // Only change code above this line
  return outerWear;
}

myOutfit();
```
### [Exercise: Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)

```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
  // Only change code above this line
  return arr.shift();
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```



