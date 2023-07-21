### Day 11: << Static Typing & Scope >> 
This README file provides a brief overview of the JavaScript lessons focusing on scopes in JavaScript & Types in JavaScript. These lessons explore the concepts of scope and data types, delving into their implementation and emphasizing their importance and core use in JavaScript.

## Lesson 1: < Static Typing > 
The first lesson is all about the concept of static typing in javascript, static typing involves specifying the type each variable in our code, all types are checked before excution (compile time).

benefits of Typescript and Flow:
- Catch type-related mistakes.
- Communicate type intent
- Provide IDE feedback.

  Typescript coding example:
  ```ts
  const fname : string = "Bashar";
  fname = {fname: "Bashar";} // ts will return an error specifying that assigning an object-type value to a string one is not allowed.
  ```
  when assigning a value to a variable without specifying its type, TypeScript sets its type to the assigned one implicitly.

  You can also make your own type in TypeScript using `type`.
  Coding example:
```ts
type Person = {
  name: string;
  age: number;
};

const aGuy : Person {
    name: "Bashar",
    age: 20;
}
```

## Lesson 2: << Scope >>
Scopes in JavaScript represents the accessibilty of some variable in a certain place in our code.
- During compilation, JavaScript Engine sets up the scope.
- JavaScript is lexically scoped language, meaning scopes are determined prior to excution time.
- Shadowing is having 2 variables with the same name and both are declared in different scopes.
- During Excution, when looking up for a value in a certain scope, if not found, search will expand to a larger scope.
- Firing a variable with the value of `null`/`undefined` with paranthesis (as a function)-> will result a TypeError.
- in case of strict mode is off and not finding the declaration of some variable, JS will look in a larger scope, if still not found even in global JS will create the variable and its scope will be global. which is called "Dynamic Scope".
- Nested scopes are a thing, making a function inside a function, the inner function can still access the outer function's variables but not the opposite.

Coding Example:
```js
function Div3() {
  const rating = -1;
  function Div4() {
console.log(rating); //will output -1 if 
}
Div4();
}
Div3();
```
## < Exercises provided by the GSG Team >

[Problems' Statements](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

### Q1 Solution:
```ts
interface HWType {
  text : string;
}
interface CBType {
  bool : boolean;
}
interface objType {
  x: string,
  y: number;
}



const sayHelloWorld = new Promise(resolve, reject => {
  resolve("Hello world!");
});

const checkBoolean = (boolean) => new Promise(resolve, reject => {
  if (boolean) {
    resolve(boolean);
  } else {
    reject(`Input is false :(`)
  }
})

const returnObj = new Promise(resolve, reject => {
  resolve({
    x: "meow",
    y: 45,
  })
})

const promisesArray : [Promise<HWType>,Promise<BCType>,Promise<objType>] = [sayHeloWorld, checkBoolean, returnObj];

const convertToObj = (array : [Promise<HWType>,Promise<BCType>,Promise<objType>]) => {
let obj ={};
for(let iterator of array)
{
const ans = await iterator();
Object.assign(obj,ans);
}
return obj;
}

```

### Q2 Solution:

- A) undefined, undefined, undefined
- B) 1, undefined, ReferenceError
- C) 1, ReferenceError, ReferenceError
- `D) 1, ReferenceError` => that's the right answer.

### Q3 Solution:

- `A) undefined, ReferenceError` => that's the answer.
- B) 1, undefined, ReferenceError
- C)undefined, undefined, ReferenceError
- D) 1, ReferenceError

### Q4 Solution:
- A) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 36, 2, 3 ]
- B) [ 36, 100, 45 ] | [1, 2, 3 ] | [ 36, 100, 45 ]
- `C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1,100, 45 ]`
- D) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1, 2, 3 ]
