### Day 11: << Static Typing & Scope >> 
will be filled later
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
