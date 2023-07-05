# Day 2: Expressions, Arrays, and Objects
The following README file provides a concise overview of the JavaScript lessons covering expressions, arrays, and objects. 
Within these lessons, we delve into the utilization of expressions to derive values, the manipulation of arrays, as well as the creation and manipulation of objects.

## Lessons Summery
### Lesson 1: < Expressions >

Expressions are considered as fundemetnal knowledge of the JavaScript language and any other language, here are the key points covered in today's lesson:

first off an expression is a combination of code elements in a programming language that evaluates to some value.

- Expressions in JavaScript produce values: so when JavaScript encounters an expression it processes it and produces a value equivalent to that expression.
- They can be simple, like variables or literals.
- They can also be complex, involving operators and functions.
- Expressions are used for operations and assigning values.
- JavaScript allows us to store expressions by a declaration and an assignment of them as variables.
- We can declare and assign varibles using `let` and `const` and `var` keywords.
- JavaScript evaluates expressions based on the order of operations and resolves them to a value.
- Statements are different from expressions, as statements instruct JavaScript to perform actions.

### Lesson 2: < Arrays > 

Arrays are data structures used to store multiple values in a single varible, which makes it much easier to control these varibles using a certain index and braces as this syntax -> ArrayName[idx];
Key points covered:

- Arrays could have elements of the same type or a mix of types at the same instance.
- Arrays as builtn Objects have some properites as functions that we can make some use of, some breif examples:
  `array.sort()`,`array.slice()`,`array.push()`,`array.shift()` etc..
- as arrays are builtin objects they have properties, a good example is the `.length` property which returns a number which represents the size of the array.
- Some array methods mutate the original array, while others create a new copy without modifying the original array.
- Immutable data and variables are preferred to avoid unintended data mutations.

### Lesson 3: < Objects >

Objects are considered as data structures that allow us to store and organize data and functionality at the same instance. Here are some key points covered:

- Objects is a collection of key-value pairs, where the key is a string that represents a properity and is associated with a value of any type.
- there are 2 ways to access objects in javascript, one way is to use the dot notation `objectName.name` or by using brackets `objectName["name"]`.
- Objects can have keys associated with functions as values which we call "methods" -> `objectName.func()`.
- Nested objects are a legal thing in javascript and you can make an object of literally anything such as an object that contains another object which contain and array of values.
- there exist too many builtin objects such as `document`, `strings`,`arrays`,`Math` and `console`.

## Code Examples
```javascript
//Lesson 1
true
"String" + "expression"
(1+14)*2%5
let name;
name = "Bashar";
let age = 19;
let havePet = false;
//HTML example
let squares = document.querySelectorAll(".square");

//Lesson 2
const arr = ['a','b','e','d','c']; // creates a variable arr and assigns ['a','b','e','d','c'] to it.

arr[2] = 'x';
console.log(arr[2] + arr[0]); // outputs the string "xa".

console.log(arr.length); // this will output the array's size which is 5.
//Array methods:

arr.sort() // sorts the array to ['a','b','c','d','e'].

let newarr = arr.concat(['z','x','y']); //as the arr.concat will return the resulted array and it will be assigend to newarr and thus it  will equal to ['a','b','c','d','e','z',,'x','y']

let temp = newarr.push('t'); //temp will have the value of the new length of the array.

//Lesson 3
const person = {
    name: "Bashar",
    age: 19,
    weight: 75,
    adress: {
        country: "Palestine",
        city: "Hebron",
        street: "Nimra"
    },
    children: null,
    greet: function () { console.log("sup bruv"); }
};
console.log(perosn.name) //this will output "bashar".
console.log(person.adress.street) // this will output "Nimra".

```

## Gaza Sky Geeks Code Exercises!

### [Exercise: Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

```javascript
// Setup
const contacts = [
    {
      firstName: "Akira",
      lastName: "Laine",
      number: "0543236543",
      likes: ["Pizza", "Coding", "Brownie Points"],
    },
    {
      firstName: "Harry",
      lastName: "Potter",
      number: "0994372684",
      likes: ["Hogwarts", "Magic", "Hagrid"],
    },
    {
      firstName: "Sherlock",
      lastName: "Holmes",
      number: "0487345643",
      likes: ["Intriguing Cases", "Violin"],
    },
    {
      firstName: "Kristian",
      lastName: "Vos",
      number: "unknown",
      likes: ["JavaScript", "Gaming", "Foxes"],
    },
  ];
  
  function lookUpProfile(name, prop) {
    // Only change code below this line
    for(let o = 0; o < contacts.length;o++)
    {
      if(contacts[o].firstName === name)
        return contacts[o].lastName;
    }
    return "No such property";
    // Only change code above this line
  }
  
  lookUpProfile("Akira", "likes");
```

### [Exercise: Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)

```javascript
function forecast(arr) {
    // Only change code below this line
    return arr.slice(2,4);;
  }
  
  // Only change code above this line
  console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```

### [Excercise: Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)

```javascript
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence = ["learning", ...fragment,"fun"]; // Change this line
  return sentence;
}

console.log(spreadOut());
```
