# Day 1: Introduction to JavaScript, DOM, Values & Data Types, and Operators

In my JavaScript learning journey, Day 1 was filled with important concepts. This README provides a summary of the key points covered. During this day, I delved into the fundamentals of JavaScript, starting with an introduction to the language itself. Additionally, I learned about the Document Object Model (DOM), values, data types, and operators. To reinforce my understanding, I dedicated time to solving three coding exercises, allowing me to practice and enhance my skills.

## Lesson Summary
<*> Introduction to JavaScript: During my exploration, I gained knowledge about the fundamental aspects of JavaScript as a programming language. I familiarized myself with its integral role in web development and discovered the extensive array of applications it offers.

<*> DOM: During my exploration, I uncovered the concept of the Document Object Model (DOM), which represents the hierarchical structure of HTML documents as a tree-like arrangement. This hierarchical representation not only enables dynamic manipulation and interaction with web pages using JavaScript but also assists the programmer in effectively accessing and modifying various elements within the page. It proves to be a valuable tool for developers, empowering them to navigate and manipulate the DOM effortlessly.

<*> Values & Data Types: In my journey, I explored JavaScript's value and data types, including strings, numbers, booleans, null, undefined, and objects. I also learned how to declare variables and assign values to them.

<*> Operators : I acquired comprehension of diverse operators within JavaScript. These encompass arithmetic operators for mathematical calculations, comparison operators for value comparisons, and logical operators for combining conditions.

## Code Examples
```javascript
(DOM)
//Accessing by ID
console.log(document.getElementById("id")); // retrieves a single element with the specified ID.
console.log(document.querySelector("#id")); //retrieve the first element with the ID.
console.log(document.querySelector("#id")); //returns a collection of elements that match a given ID.

//Accessing by ClassName.
console.log(document.getElementsByClassName("classname"));
console.log(document.querySelectorAll(".classname"));
console.log(document.querySelector(".classname"));

//Accessing by Tag name.
console.log(document.getElementsByTagName("tagname"));
console.log(document.querySelectorAll("tagname"));
console.log(document.querySelector("tagname"));

//Applications 1
console.log(document.querySelector("#p1").textContent); // outputs the text of the first element with the id of p1
console.log(document.querySelectorAll(".square").length); // outputs the number of squares were in the tic tac toe example.
console.log(document.querySelector("h2").textContent); // outputs the text contained in the first element with the tagname of h2.

//Applications 2
document.querySelector("#p1-name").textContent = "Bashar"; // will change the text content of the first element with the ID of "p1-name".

(Values and Data Type)
let val = "String"
let age = 10;
let ok = true;
let nullval = null;
let undefval;

typeof (oprand) // returns a string containing the type of that oprand.

console.log(typeof val); // this will output: "String".
console.log(typeof age); // this will output: "Number".
console.log(typeof ok); // this will output: "boolean".
console.log(typeof nullval); // this will output: "null".
console.log(typeof undefval); // this will output: "undefined". although it should be null but it's a special case.

(Strings!)
let str = "Hello World"; //declaring and initializing the variable str with the value "Hello World".
//some of its methods!
console.log(str.length); // outputs the size of the string
console.log(str.indexOf("Wo")); // outputs the first index of a substring match. else it returns -1;
console.log(~("Palestine").indexOf("Pal") ? "Yes" : "No"); // this is another example of using indexOf() to either check if a substring exists or no.
console.log(str.lastIndexOf("o")) // it will output the idex of the last appearance from left to right of the given substring.
console.log(str.includes("No")); // this will either return true when the givern substring exists in the original strings else it will return false;
console.log(str.toUpperCase()); //this will output the same string but with all characters being capital letters.

```

## Gaza Sky Geeks Coding Exercises!
### [Exercise: Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)
```javascript

let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a *= 5;
b *= 3;
c *= 10;
```

### [Exercise: Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

```javascript
let myStr ="This is the first sentence. ";
myStr += "This is the second sentence.";
```

### [Exercise: Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)

```javascript
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[(lastName.length)-2]; // Change this line

```












