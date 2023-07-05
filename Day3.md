# Day 3: Quiz Project and Functions 
The following README file provides a concise overview of the JavaScript lessons covering the Quiz Project, Functions, and the usage of let and const scopes. Within these lessons, we delve into the process of constructing a quiz project using JavaScript, while also exploring the fundamental concepts and implementation of functions, as well as the utilization of let and const for variable scoping in JavaScript.

## Leeson 1: < Quiz Project > 

in this lesson we were asked to make a project which represents a yes-no answered quiz with the explanation for either answers.
we were specifically asked to use everything we've learned in JavaScript so far to do so.

For a more detailed understanding of the project, please continue reading.

- JavaScript Pop Quiz Overview: at first we had a concise overview of the JavaScript pop quiz. this quiz served as a test of our knowledge regarding the material covered thus far. Within this section, we explored the components of the quiz project, such as script tags and code comments and what they were used for.
- DOM exercise & Declaring and Assigning Variables: as mentioned this quiz serves as a test of our knowledge of the coverd topics earlier, this surely includes DOM, this task involved declaring variables such as `statement`, `optionButtons` and `explanation`, as well as creating the object which contains the information needed to be displayed and compared with user's choice.
- Setting Statement Element: This one involved changing the question displayed by accessing the HTML element which is assigned to `statement` variable and changing its content to the content that exists in fact.statement.



##Lesson 2: < Quiz Project Functions > 

### << Functions >>

so basically in this sublesson we delved into the world of funcions and their behaviour, here are the key points of what we've covered.

- Functions are essentially reusable blocks of code that can accept arguments, known as parameters, and perform operations involving these arguments. They may also optionally return values as results.
- Functions will always return a value, so there was no specific value to be returned the function will return an undefined value.
- there is a difference between arguments and parameters though, parameters are variables listed in the function's declaration whereas arguments refer to the actual values passed into a function when it is called.
- If you send fewer arguments than the number of parameters defined in a function, the missing parameters will have the value of `undefined`.
- Arrow Functions: is a new type of funcions that serves the same as the "normal" function but with less typing.
- When the function body consists of a single expression, the curly braces and the `return` keyword can be omitted.

### Code examples of << Funcions >>

``javascript
//An example of a normal function
function devide(a,b) { //begins with `function` keyword.
    return a/b; // returns a number
}

//Same example but implemeted as an arrow function
const devide = (a,b) => a/b; // returns the same output as the normal funcrion.

//undefined return value.
function devide(a,b) {
console.log(a/b); //outputs it
}
console.log(devide(1,2)); //outputs the number then "undefined".

//you can write a one paramertized arrow function as follows:
const newFunc = a => a*a; // will return the value of n*n.

//Arrow function with multiple statements.
const newFunc = a => {
conspole.log(a);
return a*a; // outputs a value and then returns a number of value n*n.
}

```

### <<Scopes in JavaScript >>

Just as any programming language JavaScript has the concept of variable scopes, scopes actually define the limits where some variables are accessable.
JavaScript has two types of scopes: local and global. local scopes are defined within functions or specific blocks, which are enclosed by `{}`, while global scopes are not limited to any specific local area.

In ES6, the `let` keyword was introduced as an alternative to `var` for declaring variables. some of the key diffferences are covered as follows:





