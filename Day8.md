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

## Lesson 1: << Promises >>


  
