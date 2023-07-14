# Day 7: Closure
The following README file offers a concise introduction to the JavaScript lessons on JavaScript Closure. These lessons delve into the concept of closure in JavaScript, covering its implementation and highlighting its significance. They provide a thorough understanding of closure fundamentals, effective usage, and its impact on code execution.

## Lesson 1: << Closure >>
A closure is basically a feature in JavaScript that allows a function to retain access to variables from its outer scope, enabling the function to maintain references to the data it has used within a specific execution context after the latter has been terminated. key points to cover:

- Whenever a Function Excution Context (FEC) is created, a live store of data (variable environment) is associated with it, and whenver it terminates (function excution has reached to an end) the local memory gets deleted except for the return value.
- In case of returning a function that has been defined along with its variables inside the outer function(which returns the definition of the function only), it also returns the data that surrounds that particular function in the current (FEC) local memory and holds it to outer( in case of having one outer function this is global) memory, this is known as "backpack".
##Coding Example
```javascript
function outer() {
  let counter = 0;
  function incrementVal() {
  counter++;
}
return incrementVal;
}
const newFunc = outer(); // newFunc has the full definition of incrementVal but with a new associated name. And a `backpack` that has all the data that incrementVal function needs for excution. // counter = 0;
newFunc(); //counter = 1
newFunc(); //counter = 2;
const newFunc2();
newFunc2(); //counter 1;
newFunc2(); //counter =2; //newFunc2 has its own backpack which differs from newFunc's backpack.
--------------------------
//another code:
let counter =0;
function outer() {
  function incrementVal() {
  counter++;
}
return incrementVal;
}
const newFunc = outer();
newFunc(); //counter = 1;
newFunc(); //counter = 2;
const newFunc2();
newFunc2(); //counter 3;
newFunc2(); //counter =4;
```

### Coding Exercises provided by the GSG Team
[Problems Statements respectively](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)

### Problem #1 Soltuion
```javascript
const createCounter = val => {
    return ()=>{val++; console.log(val)};
}
```
### Problem #2 Solution
```javascript
const calculateAverage = arr => ()=> {console.log(arr.reduce((prefix,currVal)=>prefix+currVal,0)/arr.length);};
```

### Problem #2 Solution
```javascript
const powerOf = base => exp=> Math.pow(base,exp);
```

### Problem #3 Solution
```javascript
const compose = ...functions => (val)=>{
for(let o =0; o < functions.length;o++)
  val = functions[o](val);
return val
}
```
