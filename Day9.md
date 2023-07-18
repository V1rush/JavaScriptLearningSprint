### Day 9: Classes & Prototypes

This README file provides a brief overview of the JavaScript lessons focusing on Classes and Prototypes. These lessons explore the concept of classes and prototypes in JavaScript, discussing their implementation and emphasizing their importance. They aim to provide a comprehensive understanding of classes and prototypes, including fundamental concepts, practical usage, and their impact on code structure.

## << Introduction >>

Object Orianted Programming (OOP) aims at producing a program that is an easy to understand, extend, perform efficiently and adding other features as we wish. By organizing code into instances of objects, so to achive all that we're to make a program that has 2 users as objects and each has their own attributes but with the same functionality.

We'll be delving into 4 ways of fixing that base code to provide the best performance as possible

## < Base Code >
```javascript
const user1 = {
  name : "Bashar",
  score : 4,
  increase : function() {
      user1.score++;
  }

const user2 = {
  name : "Ali",
  score : 3,
  increase : function() {
      user2.score++;
  }
}
user1.increase(); // will increase user1.score to 5.
user2.increase(); // will increase user2.score to 4.
```
This code violates a principle of general programming known as "DRY" => (Don't Repeat Yourself). DRY emphasizes avoiding code duplication and promoting code reusability, so basically the implemention is the same for both user1 and user2 and we'll be working on that in #Solution 1.

## < Solution 1: Function >

```javascript
function userCreator(name, score) {
 const newUser = {};
 newUser.name = name;
 newUser.score = score;
 newUser.increment = function() {
 newUser.score++;
 }
 return newUser;
};
const user1 = userCreator("Bashar", 4);
const user2 = userCreator("Ali", 3);
user1.increment();
user2.increment();
```
Well, this code is a bit better since coding blocks are not repeated unnecessarily.
but we're still facing some problems with this solution which are:
- if we're to make many users all of these users will have the same implementation for functions which clearly is a problem, could it be avoided? of course and we'll delve into it in the next solution.
- what about if we made thousands of copies and whooop, we wanna change a function or add one, then we have to all over code which is very exhausting!

## < Solution 2: Prototype Chain>
```javascript
function userCreator (name, score) {
 const newUser = Object.create(userFunctionStore);
 newUser.name = name;
 newUser.score = score;
 return newUser;
};
const userFunctionStore = {
 increment: function(){this.score++;},
 login: function(){console.log("Logged in");}
};
const user1 = userCreator("Bashar", 4);
const user2 = userCreator("Ali", 3);
user1.increment();
user2.increment();
```
the basic idea of this solution is just to take the functions repeated (all the functions) as a common factor and put them in a single object. but how are we going to access them?
basically what `Object.create(userFunctionStore)` does is that it it creates a new object but has like properity which is ``__proto__`` this properity is inside every object and `Object.create(userFunctionStore)` links that properity with the object that has the functions stored in.

so if we're to access  `user1.increment()` we can't really find it there, so if it's not a properity in user1 it looks up for it in the object linked in the `__proto__` property which is userFunctionStore in our case

this is the prototype chain.
the term  "prototype chain" describes the sequence of the sequence of linked objects formed through the `__proto__` properity. This terminology emphasizes the relationship between objects and their prototypes.

Confusion: alright that's for a single user, what if we have 2 users like my example, and we fired both functions, how do we get the information that when we fire `user1.increment()` we're really dealing with user1 data not user2?
short answer: `this` keyword.

whenever I use `this` in the `userFunctionStore` function it will point to the right hand side. 
example: 
`user1.increment()`, `this` will point to `user1`.

but if I declare it inside a whole function, as follow:
```javascript
const userFunctionStore = {
 increment: function() {
 function add1(){ this.score++; }
 add1();
 }
};
```
when using a regular function (not an arrow function) this will refer to anything depending on the invokation scope.
for example if it was invoked in a global context it will refer to the `window` which is the global object for the browser environment.
another example is an invokation inside an Object, `this` will then refer to the object itsself.

as I said stated earlier that's just for regualr functions, arrow functions behave differently.
```javascript
const userFunctionStore = {
increment: function() {
const add1 = ()=>this.score++;
add1()
}
};
```
bascially dont "توجع راسي ولا اوجع راسك", `this` in arrow functions point to where they were origianlly stored.


- if you wanna check wheather an object has a some properity you can do it by `objectName.hasOwnProperity('properityName')`

## < Solution 3: `new` >:
```javascript
function userCreator(name, score) {
  this.name = name;
  this.score = score;
};
userCreator.prototype // {}; every functioon has a prototype object.
userCreator.prototype.increment = function(){
 this.score++;
}
const user1 = new UserCreator("Besho", 4);
const user2 = new UserCreator("Ali",3);
```
well this is actually similar to the last approach but it's more thrilling, imagine that every function in javascript could be an object in the same time.
- Functions are bascially functions and objects at the same instance!
    which actually means that they can have properities, in fact all objects have an object type properity which is called `prototype`.
bascially we're just gonna make use of it my disposing the object we were saving our functions in and just switching to the prototype object instead.

so now just by using the `new` keyword, we create a new object of userCreator. and we can access its properities directly on user1 for instance because it is defined on the object itself and we can use any function defined in the `prototype` properity in `userCreator`.

## < Solution 4: `Class` >
```javascript
class UserCreator {
 constructor (name, score){
 this.name = name;
 this.score = score;
 }
 increment (){ this.score++; }
 login (){ console.log("login"); }
}
const user1 = new UserCreator("Besho", 4);
const user2 = new UserCreator("Ali",3);
user1.increment();
```
it does the same thing as the previous example but this one looks better :)

what's also note worthy is that we're capitalizing the first character to prevent mistakes from our fellow programmers >_>. 
