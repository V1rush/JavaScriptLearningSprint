Day 12: << Function Expressions, Advanced Scope & Closure >>
The Scope & Function Expressions, Advanced Scope & Closure README offers a concise introduction to the fundamental concepts of scope and function expressions in JavaScript. These lessons delve into the implementation of scopes and function expressions, highlighting their significance and core applications. The primary objective is to ensure a strong comprehension of scope and function expressions in JavaScript, encompassing practical usage and their impact on code structure.

## << Function Expressions >> 
It seems like we can assign functions to variables and access them through the names of these variables.

*Question* why should I used named function expressions?

- It's a reliable function name-reference (for recursive functions).
	      -* if's an eventhandler and it needs to reference itself to unbind itself
        -* it's useful if you wanna access any property of that function's object=> length, name.
- More debuggable stack trace.
	    *- if you use a name for your function express, it will show up in the stack trace.
- More self-documenting code (code readablility).
	    *- having anoynymous name will force you to read the function's body to know what it does, but if it had name, its name will give an indication of its job 

Basically a function expression can be any statement in the code that has a `function` keyword within the statement but not in the beggining of that statement.
Also function expressions are not hoisted, meaning you can never access them before assigning them to a variable during run time.
so if we are to try it out in code:

```js
theory(); // this will throw an ReferenceError.
const theory = function funcExpression(){console.log("Hi")}
```

## << Advanced Scoping >> 
When we think about lexical scope we think about something that is fixed at auther time (compile time) and it's predictable and not affected by run-time conditions
Dynamic Scope is the opposite. meaning that they can affect the scoping. 

Dynamically scoped function in my POV is more like a function that takes its resources from an outsided scope which it relies on.(it's more theoratical than a real thing)


IIFE (Immediately Invoked Function Expression): it's a design pattern in JavaScript that allows us to create a new function scope to encapsulate variables nd avoid polluting the global scope with variables that are used only within the function. 

Coding Example:
```js
const val = "global"
function newFunc() {
console.log(val);
};

this can be written as this:
(function newFunc() {
console.log(val);
};)();
```
### < Hoisting > 
To run a code in JavaScript you've to go through 2 phases, creation phase and excution phase, in creation phase you're taking all function definitons and variable declaration and saving them up in memory in preparation for the next phase which is excuting based on these information.
also scope planning happens to let javascript know what are the scopes in that code
hoisting is bascially the idea of moving the declaration of a variable and functions definitions to the top of their own scope.
`const` & `let` does not work that way, for example:
```js
console.log(x); // this will give a referenceError.
let x = 10;
console.log(y);// this will output: undefined
var y =10;
func(); // this will output 10.
function func() {
console.log(x);
}
```

## << Closure >>
Closure is when a function "rememebrs" its lexical scope even when the function is excuted outside the lexical scope.


## < Exercises provided by the GSG Team >
[Problems' Statements](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

### Q1 Solution: 
```js

const exampleNormalFunc1 = (a, b, c) => {
  return a * (b + c);
}

const exampleNormalFunc2 = (x, y) => {
  return x * y;
}

const exampleNormalFunc3 = (string) => {
  return string + " " + string + " " + string + "!";
}


const arrowHOF = (normalFunc) => (...args) => {
        const result = normalFunc(...args);
            return (val = 1)=> {
          for(let o = 0; o < val; o++) {
                console.log(result);
      }
      }
}

const hofNormalFunc1 = arrowHOF(exampleNormalFunc1);
const hofNormalFunc2 = arrowHOF(exampleNormalFunc2);
const hofNormalFunc3 = arrowHOF(exampleNormalFunc3);

hofNormalFunc1(3, 4, 5)(2); // logs 60 twice
hofNormalFunc2(20, 35)(4); // logs 700 four times
hofNormalFunc3("Meow")(); // logs "Meow Meow Meow!" once

```

### Q2 Solution:

```js
// Example object
const obj = {
  name: 'John',
  greet: function (greeting) {
    console.log(`${greeting}, ${this.name}!`);
  }
};

const preserveThis = (func) => {
  return func.bind(obj);
};

// Wrap the greet function using preserveThis
const preservedGreet = preserveThis(obj.greet);

// Call the wrapped function as a method of the object
preservedGreet('Hello'); // Output: "Hello, John!"
```

### Q3 Solution:
**A**

```js
function outer1() {
  var x = 10;

  var inner1 = function() {
    console.log(x);
  };

  inner1();
}

outer1(); // Output: 10
```
Basically what happens here is that the `outer1` function has a variable `x` with the value of 10, and at the same instance has an inner function `inner1` which doesn't find `x` in its scope so it expands the scope to the scope of `outer1` which has `x` defined and has the value of `10` so it outputs it.


**B**
```js
function outer2() {
  var x = 10;

  var inner2 = function() {
    var x = 20;
    console.log(x);
  };

  inner2();
}

outer2(); // Output: 20
```
So now x is defined within the `outer2` function, and its value is `20` but we also do have an `x` that has been declared and assigend earlier in the `outer1` function, of value `10`, but the thing here is that when `outer2` is invoked it does not make a new variable cause it was declared with `var` not with `const` or `let` so it just modifies it to 20 instead which is the output.

## < Advanced scope: >

[Problems' Statements](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)

### Q1 Solution: 

```js
for (let i = 0; i < 5; i++) {
    setTimeout(function() {
      console.log("value of [i] is: ", i);
    }, 100);
}
```
using `var` would be wrong if you want to get the permuation of 0 to 4 because `var` is a function scoped declaration keyword, on the other hand though, let's make a use of that for loops create a new block each iteration, so we can assign a new `i` to each block which is actually happening in the code I provided.
to be more precise though, when the loop is over and all `setTimeout` Functions are called and waiting on the event queue, they dont really have the value of `i` but more than a reference to it, and guess what, since `i` is the same across all the blocks that means when the functions are excuted they will reference the value of 5.

### Q2 Solution: 
```js
let array = [];
for (let i = 0; i < 5; i++) {
   array.push(i);
}
   console.log("Current array is: ", array);
```
we're just declaring an array and using a loop to access the array and mutate it to add 5 elements to it in each loop to make a permuation, then we just output it.

### Q3 Solution:
```js
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```
the same as Quesiton 1. `let` in each loop creates a new block for each arrow function which will be accessed when called.

## < Closure >
Q1 Solution:
```js
function privateCounter() {
	let cnt = 0;
	function incrementcnt() {
		cnt++;
	}
	function getcnt() {
	return cnt;
}
return ({incrementcnt : incrementcnt, getcnt : getcnt}); 
}
const val = privateCounter();
console.log(val.getcnt()); // 0
val.incrementcnt();
console.log(val.getcnt()); // 1
```
Q2 Solution: 

Implemented using DP in JS (poorly but acceptable lol)
```js
const mx = 1e8;
let dp = new Array(mx);
dp[1] = 1;
dp[0] = 0;
function fib(val) {
    if(val<=0)
        return 0;
    if(dp[val] !== undefined)
        return dp[val]
    return dp[val] = fib(val-1)+fib(val-2);
    
}
console.log(fib(7));
```

