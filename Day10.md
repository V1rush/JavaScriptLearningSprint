### Day 10: Introduction & Types
This README file provides a brief overview of the JavaScript lessons focusing on various JavaScript Date Types. These lessons explore the concept of data types in JavaScript, discussing their implementation and emphasizing their importance and their core use. They aim to provide a very solid understanding of data types in JavaScript, including fundamental concepts, practical usage, and their impact on code structure.

## << Introduction >> 

"Whenever there's a divergence between what your brain thinks is happening, and what the computer does, that's where bugs enter the code."
It's our responsibility as developers to know all the details about the tools we're working with in order to avoid unwanted bugs and ensure the success of our projects. Being well-informed about the tools and technologies we use empowers us to make better decisions, write more efficient code, and build more robust and reliable software.

### < Coding Example >
```js
let x = 0;
x++;// returns the value of x then increments it by one, which could really mean in javascript as basic as x = x+1;
++x; // returns the value of x+1.

let str = "5";
++str; // this must be "5" + 1 which is '51', but we actually get the number 6!
//because in the specs it converts it to a number format then does the str + 1 operation so it returns 6!
```

## << Lesson 1: Types >> 

- Question: is everything in JavaScript an object?
   * Short answer is no, most of JavaScript values can behave as objects but that does not make them objects.
**Primitive Types**
if we're to advance in javascript we're stricted to get know it's fundementals, one of any langauge's fundementals is its primitive types which are the building blocks.
JavaScript Primitive Types are:

- undefined
- boolean
- number
- string
- object
- symbol - introduced in ES6 they're typically used for sudo private keys.
- bigint - is not a primitive type in javascript specifications yet but a precentage of 95 that it will be added in the future.

  PS: Functions and Arrays are subtypes of Object type!
    functions are like "callable objects".

- JavaScript variables DOES NOT possess any kind of types, but values does!
- if we wish to know the type of the value that a variables possesses we're ought to use `typeof`
- `typeof` never fails us, it always returns a non-empty string whart-so-ever.

**undefined vs. undeclared vs. uninitalized**

undeclared variable: it represents a variable that has not been declared using var, let, or const.
  - Trying to access such variable will issue a ReferenceError.

undefined variable: it means that we have some variable but sadly it does not possess any kind of value at the moment.
  - It means that we've declared the variable but we have not assigned a a value to it not so ever.

uninitialized variable: a variable with undefined value set to it.

PS. undefined variables and uninitialized variables are actually the same.

** Special Values **
JavaScript possess two special values that might give a headache while understanding but they're a must to learn anyways.
JavaScrip special values:

*NaN*

-NaN -> Not a Number.
NaN is a member of the Number data type in JavaScript, but it is considered to be an invalid number.
it is also the only number that does not equal to itsself.
```js
let age = 0/1; // age is NaN now.
console.log(age === age ? "equals" : "doesn't equal");// output is "doesn't equal"
```
we also have this function `isNaN()` which tells us if the given arguemnt possess the NaN value or not.
- it has some glicthes tho if we're gonna test out like this: `isNaN("Bashar");` it is actually gonna return true but that's not true at all! that's a string my name!
    it bascially transfers the string "Bashar" to a  number and guess what, "Bashar" is not a number -> NaN! so it returns true.
- what if we wanna have more striction?
    - we have `Number.isNaN("Bashar");` which will not convert it to a number so it will give the true value.
    - this will output `false` by the way.

*Negative Zero*

I know it sounds crazy, and I know if you're a mathematician you're making fun of me now, but -0 is a thing is JavaScript.
```js
0 === -0 // this will equal to true;
let x = -0;
x.toString(); // x is 0;
//but if we use a builtin checker that is more strictive than the triple equals it will give us this output
Object.is(-0,0); // according to the upper lines of code it must return true, but guess what, it returns a big FALSE.
```

### An excercise provided by Kyle Simpson.

Make your own Object.is(...).

```js
if(Object.is || true)
{
Object.is = function ObjectIs(x,y) {
  const xNegZero = isNegZero(x)
  const yNegZero = isNegZero(y)
if(yNegZero || xNegZero)
    return yNegZero && xNegZero;
}
else if(isNaN(x) && isNaN(y))
{
    return true;
}
else {
return x === y;
}
function isNegZero(val) {
  return ((1/val) === -Infinity);
}
function isNaN(val) {
return val !== val;
}

//test case:

console.log(Object.is(42,42) === true);
console.log(Object.is("foo","foo") === true);
console.log(Object.is(false,false) === true);
console.log(Object.is(null,null) === true);
console.log(Object.is(undefined,undefined) === true);
console.log(Object.is(NaN,NaN) === true);
console.log(Object.is(-0,-0) === true);
console.log(Object.is(0,0) === true);

console.log(Object.is(-0,0) === false);
console.log(Object.is(0,-0) === false);
console.log(Object.is(0,NaN) === false);
console.log(Object.is(NaN,0) === false);
console.log(Object.is(42,"42") === false);
console.log(Object.is("42",42) === false);
console.log(Object.is("foo","bar") === false);
console.log(Object.is(false,true) === false);
console.log(Object.is(null,undefined) === false);
console.log(Object.is(undefined,null) === false);
```

## < Exercises provided by the GSG Team > 
[Questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/146299d463da8ad3a5dfeb926ad8153c2c6a11bd/learning-sprint-1/week3-day1-tasks/tasks.md)

Question 1 Solution:
```js
const convertStringToNumber = (val)=> {
    return ((typeof val !== "string")? {value : val, type: typeof val} :  val++);
}
```
Question 2 Solution:
```js
const checkNaN = (val) => val!==val; // if it's a NaN it will return true.
```
Question 3 Solution:
```js
const isEmptyValue = (input)=> input === undefined? "undefined": input === null? "null": "mt string";
```
Question 4 Solution:
```js
const compareObjects(x,y) {
  if(!((typeof x === 'object') && (typeof y === 'object)))
        return [input1, input2];
  if(Object.keys(x).length !== Object.keys(y).length)
    return false;
  let keysArray = Object.keys(x);
  keyArray.forEach(iterator=> {
if(x.hasOwnPorperty(iterator) && y.hasOwnProperty(iterator))
  if(x[iterator] != y[iterator])
      return false;
});
retrun true;
}
```

