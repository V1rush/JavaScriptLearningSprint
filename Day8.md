### Day 8: Asynchronous JavaScript & Promises
This README file provides a brief overview of the JavaScript lessons focusing on Asyncronous programming and promises. These lessons explore the concept of async programming and promises in JavaScript, discussing their implementation and emphasizing their importance. They aim to provide a comprehensive understanding of async programming and promises, including fundamental concepts, practical usage, and their impact on code execution.

## Lesson 1: << Asynchronous JavaScript >>
The lesson covers the following key points:
- JavaScript is a single threaded language, meaning that it can excute one line of at a time in order.
- With that in mind, how come Asynchronous JavaScript is a thing?
  quick answer to that is: Simply, JavaScript is still a synchronous language, but there are certain functions that can take a significant amount of time to execute. so the browser handles these functions in an asynchronous manner to prevent blocking the execution of other code.
- Any web browser contains:
   - JavaScript Engine
   - Parser as part of the Rendering Engine.
   - HTML DOM - can be accessed in JS by using `document`.
   - Timer - can be accessed by using `setTimeOut()`.
   - Console - can be accessed by using `console`.

## Coding Example for < Asynchronous JavaScript >
```javascript
setTimeOut(()=> console.log("Hello"),1000); // excute the callback function after 1000ms.
console.log("First?");

/*
this code outputs:
First?
Hello
*/
//Ex2

setTimeOut(()=> console.log("Hello"),0); // excute the callback function after 1000ms.
console.log("First?");

/*
this code outputs:
First?
Hello
*/
//JavaScript will put the setTImeOut() function in a queue to excute after the call stack is done excuting the code. meaning even if it is delayed by 0ms it will still output when the call stack is empty.
```

## Lesson 2: << Promises >>
Promises are special objects that are built in the JavaScript to keep track of web browser's callings through JavaScript, an example of that the latter is `fetch` function, which upon calling immediately returns an object that contains a value, onfulfillment & onrejection properities.

- `fetch` is a two-pronged facade function that initiates a network request (more like an https request to get data) and immediately returns a promise placeholder object with the properities mentioned earlier.
- when the task is completed and data is fetched, it is set to the value property of the place holder object.
- in order for us to manipulate this data we can use the `.then` function.
- `.then` is a function that can access the hidden properity of the placeholder object which automatically triggers the functions inside of it which it the `onfulfillment` properity.
- using the `.then` is the only way to access it since it's a hidden properity.

This brings us to the rules of the delayed asynchronous code
  - All functions that return promises are put in a microtask queue, while callback functions are queued in a different queue called "callback queue".
  - microtask queue has a higher priority than the callback queue, meaning that after the regular code is compelted and the call stack is empty, it checks the microtask queue first and excutes all the functions in it then it proceeds to the callback queue.

- Error handling using `fetch` is quite easy, we can simply chain a fetch function with a `.then` and a `.catch` callback functions, `.then` is for a successful fetch of data and `.catch` is for an error occured while doing so. 


## Coding Examples
```javascript
function display(data) {
  console.log(data);
}

const fetchData = fetch('https://api.example.com/data');

fetchData
  .then(response => response.json())
  .then(data => display(data))
  .catch(error => console.log(error));

console.log("Me first!");
//output
//Me first!
//either the data that has been fetched from the api endpoint or an error message.
```

### Problems provided by the GSG Team

## Question 1:

You are given a function `executeInSequenceWithCBs` and some code. The task is to
modify the `executeInSequenceWithCBs` function so that it runs and executes all
the tasks inside the asyncTasks array. 

The function should return an array of messages obtained from each task's
execution.

You are only allowed to change the `executeInSequenceWithCBs` function or add new
functions/code. You cannot modify the tasks' functions.

```javascript

const task1 = (cb) => setTimeout(() => {
  const message = "Task 1 has executed successfully!";
  cb(message);
}, 3000)

const task2 = (cb) => setTimeout(() => {
  const message = "Task 2 has executed successfully!";
  cb(message);
}, 0)

const task3 = (cb) => setTimeout(() => {
  const message = "Task 3 has executed successfully!";
  cb(message);
}, 1000)

const task4 = (cb) => setTimeout(() => {
  const message = "Task 4 has executed successfully!";
  cb(message);
}, 2000)

const task5 = (cb) => setTimeout(() => {
  const message = "Task 5 has executed successfully!";
  cb(message);
}, 4000)

const asyncTasks = [task1, task2, task3, task4, task5];

const executeInSequenceWithCBs = (tasks, callback) => {}

```javascript
const executeInSequenceWithCBs = (tasks, callback) => {
const msgs = [];
    tasks.forEach(task=> {
        task((msg)=> {
            msgs.push(msg);
            callback(msg);
        });
    });
}
executeInSequenceWithCBs(asyncTasks,(msg)=>console.log("message:",msg));
```
## Question 2:

You are given a function called `executeInParallelWithPromises`, which takes an
array of APIs (represented by objects). 

Your task is to write code that fetches the data of each API in parallel using
promises. In Parallel means that the api which resolves first, returns its value
first, regardless of the execution order. 

The output of the `executeInParallelWithPromises` function should be an array
containing the results of each API's execution.

Each result should be an object with three keys: `apiName`, `apiUrl`, and
`apiData`..

```javascript
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
]

const executeInParallelWithPromises = (apis) => {}

```
## My Solution:
```javascript
const executeInParallelWithPromises = (apis) => {
    const promisesArray = apis.map(iterator => fetch(iterator.apiUrl).then(response => response.json()).then(data => ({
        apiName: iterator.apiName,
        apiUrl: iterator.apiUrl,
        apiData: data
    }))
    );
    return Promise.all(promisesArray);
}

executeInParallelWithPromises(apis).then(response=> {
    response.forEach(iterator => console.log(iterator));
}).catch(err=>console.error(err)); 

```

## Question 3: 

You are given a function called `executeInSequenceWithPromises`, which takes an
array of APIs (represented by objects). 

Your task is to write code that fetches the data of each API sequentially (one
after the other) using promises. 

In Sequence means that the api which executes first, returns its value
first.

The output of the `executeInSequenceWithPromises` function should be an array
containing the results of each API's execution.

Each result should be an object with three keys: `apiName`, `apiUrl`, and
`apiData`.

```javascript

const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
]

//modify and write your code here
const executeInSequenceWithPromises = (apis) => {}

```

## My solution:
```javascript
const apis = [
    {
        apiName: "products",
        apiUrl: "https://dummyjson.com/products",
    },
    {
        apiName: "users",
        apiUrl: "https://dummyjson.com/users",
    },
    {
        apiName: "posts",
        apiUrl: "https://dummyjson.com/posts",
    },
    {
        apiName: "comments",
        apiUrl: "https://dummyjson.com/comments",
    }
]

//modify and write your code here
const executeInSequenceWithPromises = (apis) => {
    const promisesArray = apis.map(async iterator => {
        const response = await fetch(api.apiUrl);
        const data = await response.json();
        return {
            apiName: iterator.apiName,
            apiUrl: iterator.apiUrl,
            apiData: data
        };
    });
    return promisesArray;
}

console.executeInSequenceWithPromises(apis).then(response=> console.log(response)).catch(err=> {
    console.error(err);
});
```
  
