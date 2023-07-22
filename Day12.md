Day 12: << Scope & Function Expressions, Advanced Scope & Closure >>
The Scope & Function Expressions, Advanced Scope & Closure README offers a concise introduction to the fundamental concepts of scope and function expressions in JavaScript. These lessons delve into the implementation of scopes and function expressions, highlighting their significance and core applications. The primary objective is to ensure a strong comprehension of scope and function expressions in JavaScript, encompassing practical usage and their impact on code structure.

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

### Q2 Solution: 
```js
let array = [];
for (let i = 0; i < 5; i++) {
   array.push(i);
   console.log("Current array is: ", array)
}
```




