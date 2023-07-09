# Day 5: Data Fetching & Promises, Destructuring data, Async, and Modules

The following README file offers a concise overview of the JavaScript lessons covering Data Fetching, Promises, Destructuring, Async, and Modules. Within these lessons, we explore the process of implementing data fetching, understanding promises, as well as utilizing destructuring, async functions, and modules in JavaScript. These lessons provide a comprehensive understanding of working with data fetching, handling asynchronous operations with promises and async functions, leveraging destructuring for efficient variable assignment, and organizing code using modules.


## Lesson 1: << Data Fetching & Promises >>

We mangaged to bring data from an API endpoint using the `fetch` global function, this function returns what we can call a promise and we'll dig into it later. key points were coverd in this leeson:

- Figuring out a new way to get a ready-to-use data to manipulate using the `fetch` function and an API.
- Promises are objects that represent the eventual completion (or failure) of an asynchronous operation and the resulting value.
- Promises can be in one of three states, `pending` which is the inital state and it means that fetching is still in process, `Fulfilled` meaning that the previous state is over and we successfully have fetched the desired data from the API endpoint, and lastly `Rejcected` which means that we have encountered an error or failure of a data fetching process.
- Promises are things that takes time to change states from `pending` to either `Fulfilled` or `Recjected` with that, since JavaScript is a one-threaded language, it will skip the function and continue with the other lines of code, and afterwards the skipped function will be processed.
- Await: it's a javascript operator that pasues the excution of the code until the value of some promise is either fullfilled or rejected, so it basically waits for a promise and obtain its value.

## Lesson 2: << Destructuring Data >>

Destructuring allows us to extract values from an array or an object and assign their values to individual variables. Here are some points coverd.

- Destructuring allows us to break down object's properities (or some of them) into individual properites to access them quickly rather than accessing them with the object's name.
- Destructuring Arrays is similar to objects, but 2 differences occures, first is that order does not real matter here, and you can make yourself new variable names.


## Lesson 3: << Async & error handeling >> 

We only can use `await` inside async functions or at the top level of a module. points were coverd in this lesson:

- We have constructed a function that fetches and parses it in a single function, which increases reusability.
- in order for that function to work asynchronously we added the `async` keyword.
- in order to get the value of the promise we use this syntax `await functionName(someVarible)`.
- Handling any error that could occure during this using `try` and `catch`.

## Lesson 4: << Modules >> 

Modules let us split big codebases across multiple files, which is a thing that could come in handy when dealing with huge projects. here are the main points covered:

- Understanding the differences between JavaScript modules and traditional JavaScript.
- Importing and exporting modules using `export` & `import` keywords.
- Some debugging methods, console.log() & browser debugging techniques.

## Coding Examples

### < Data Fetching & Promises >
```javascript
async function getBody(URL) {
  const response = await fetch(URL);
  const body = await response.json();
return body;
}
const result = await getBody("https://dog.ceo/api/breed/hound/list");
console.log(result)// outputs the result.
let {message} = result;
console.log(message)// this will have the value of the promise.
```

### < Destructuring Data >

```javascript
const me = {
  name: "Bashar",
  age: 20,
  country: "Palestine",
  city: "Hebron",
}
let {name,age,country,city} = me;
console.log(name) // will output : Bashar
console.log(city) // will output : Herbon

const arr = [1,2,3,4];
let {,two,three} = arr;
console.log(two) // outputs 2
console.log(three) // outputs 3
```
### < Async Functions >
//cathcing and fixing any error that occures in runtime.
```javascript
try {
async function getBody(URL) {
  const response = await fetch(URL);
  const body = await response.json();
return body;
}
}
catch(err) {
console.log("Will output when an error occurs");
console.log("An error has occured while fetching the data need");
}
console.log("Will always output")
const result = await getBody("https://dog.ceo/api/breed/hound/list");
console.log(result)// outputs the result.
let {message} = result;
console.log(message)// this will have the value of the promise.
```

### < Modules > 

```javascript
//A function that exists in module 1 which is called math.js
export function subtract(a, b) {
  return a - b;
}

//main file which is called main.js
import {subtract} from "math.js"
console.log(subtract(1,2)); //outputs -1;
```

## Doggo Quiz Code:

```javascript
<!DOCTYPE html>
<!-- saved from url=(0067)https://anjana.dev/javascript-first-steps/3-doggofetch-starter.html -->
<html lang="en-US" data-darkreader-mode="dynamic" data-darkreader-scheme="dark"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><style class="darkreader darkreader--fallback" media="screen"></style><style class="darkreader darkreader--text" media="screen"></style><style class="darkreader darkreader--invert" media="screen">.jfk-bubble.gtx-bubble, .captcheck_answer_label > input + img, span#closed_text > img[src^="https://www.gstatic.com/images/branding/googlelogo"], span[data-href^="https://www.hcaptcha.com/"] > #icon, #bit-notification-bar-iframe, ::-webkit-calendar-picker-indicator {
    filter: invert(100%) hue-rotate(180deg) contrast(90%) !important;
}</style><style class="darkreader darkreader--inline" media="screen">[data-darkreader-inline-bgcolor] {
  background-color: var(--darkreader-inline-bgcolor) !important;
}
[data-darkreader-inline-bgimage] {
  background-image: var(--darkreader-inline-bgimage) !important;
}
[data-darkreader-inline-border] {
  border-color: var(--darkreader-inline-border) !important;
}
[data-darkreader-inline-border-bottom] {
  border-bottom-color: var(--darkreader-inline-border-bottom) !important;
}
[data-darkreader-inline-border-left] {
  border-left-color: var(--darkreader-inline-border-left) !important;
}
[data-darkreader-inline-border-right] {
  border-right-color: var(--darkreader-inline-border-right) !important;
}
[data-darkreader-inline-border-top] {
  border-top-color: var(--darkreader-inline-border-top) !important;
}
[data-darkreader-inline-boxshadow] {
  box-shadow: var(--darkreader-inline-boxshadow) !important;
}
[data-darkreader-inline-color] {
  color: var(--darkreader-inline-color) !important;
}
[data-darkreader-inline-fill] {
  fill: var(--darkreader-inline-fill) !important;
}
[data-darkreader-inline-stroke] {
  stroke: var(--darkreader-inline-stroke) !important;
}
[data-darkreader-inline-outline] {
  outline-color: var(--darkreader-inline-outline) !important;
}
[data-darkreader-inline-stopcolor] {
  stop-color: var(--darkreader-inline-stopcolor) !important;
}</style><style class="darkreader darkreader--variables" media="screen">:root {
   --darkreader-neutral-background: #131516;
   --darkreader-neutral-text: #d8d4cf;
   --darkreader-selection-background: #004daa;
   --darkreader-selection-text: #e8e6e3;
}</style><style class="darkreader darkreader--root-vars" media="screen"></style><style class="darkreader darkreader--user-agent" media="screen">html {
    background-color: #181a1b !important;
}
html {
    color-scheme: dark !important;
}
html, body {
    background-color: #181a1b;
}
html, body {
    border-color: #736b5e;
    color: #e8e6e3;
}
a {
    color: #3391ff;
}
table {
    border-color: #545b5e;
}
::placeholder {
    color: #b2aba1;
}
input:-webkit-autofill,
textarea:-webkit-autofill,
select:-webkit-autofill {
    background-color: #404400 !important;
    color: #e8e6e3 !important;
}
::-webkit-scrollbar {
    background-color: #202324;
    color: #aba499;
}
::-webkit-scrollbar-thumb {
    background-color: #454a4d;
}
::-webkit-scrollbar-thumb:hover {
    background-color: #575e62;
}
::-webkit-scrollbar-thumb:active {
    background-color: #484e51;
}
::-webkit-scrollbar-corner {
    background-color: #181a1b;
}
::selection {
    background-color: #004daa !important;
    color: #e8e6e3 !important;
}
::-moz-selection {
    background-color: #004daa !important;
    color: #e8e6e3 !important;
}</style>
    
    <title>Doggo Fetch</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }
        header {
            width: 70%;
            margin: 1em auto;
        }
        main {
            max-width: 70%;
            margin: 0px auto;
            display:flex; 
            flex-direction: column;
        }
        img {
            max-width: 100%;
        }
        #image-frame {
            font-size: x-large;
            text-align: center;
            margin: 1rem auto;
        }
        #explanation, #score {
            padding: 1rem;
            text-align: center;
        }
        #options {
            max-width: 100%;
            display: flex;
            flex-direction: column;
        }
        button {
            padding: 0.5rem;
            font-size: medium;
            border-radius: 5px;
        }
        .correct {
            background-color: lightgreen;
        }
        .incorrect {
            background-color: lightpink;
        }
        .hidden {
            display: none;
        }
    </style><style class="darkreader darkreader--sync" media="screen"></style>
  <style type="text/css" id="operaUserStyle"></style><style class="darkreader darkreader--sync" media="screen"></style><meta name="darkreader" content="4a21d76f4ea546429bafc7f872fb6ae2"><style class="darkreader darkreader--override" media="screen">.vimvixen-hint {
    background-color: #7b5300 !important;
    border-color: #d8b013 !important;
    color: #f3e8c8 !important;
}
#vimvixen-console-frame {
    color-scheme: light !important
}
::placeholder {
    opacity: 0.5 !important;
}
#edge-translate-panel-body,
.MuiTypography-body1,
.nfe-quote-text {
    color: var(--darkreader-neutral-text) !important;
}
gr-main-header {
    background-color: #0f3a48 !important;
}
.tou-z65h9k,
.tou-mignzq,
.tou-1b6i2ox,
.tou-lnqlqk {
    background-color: var(--darkreader-neutral-background) !important;
}
.tou-75mvi {
    background-color: #032029 !important;
}
.tou-ta9e87,
.tou-1w3fhi0,
.tou-1b8t2us,
.tou-py7lfi,
.tou-1lpmd9d,
.tou-1frrtv8,
.tou-17ezmgn {
    background-color: #0a0a0a !important;
}
.tou-uknfeu {
    background-color: #231603 !important;
}
.tou-6i3zyv {
    background-color: #19576c !important;
}
div.mermaid-viewer-control-panel .btn {
  fill: var(--darkreader-neutral-text);
  background-color: var(--darkreader-neutral-background);
}
svg g rect.er {
  fill: var(--darkreader-neutral-background) !important;
}
svg g rect.er.entityBox {
  fill: var(--darkreader-neutral-background) !important;
}
svg g rect.er.attributeBoxOdd {
  fill: var(--darkreader-neutral-background) !important;
}
svg g rect.er.attributeBoxEven {
  fill-opacity: 0.8 !important;
  fill: var(--darkreader-selection-background);
}
svg rect.er.relationshipLabelBox {
  fill: var(--darkreader-neutral-background) !important;
}
svg g g.nodes rect, svg g g.nodes polygon {
  fill: var(--darkreader-neutral-background) !important;
}
svg g rect.task {
  fill: var(--darkreader-selection-background) !important;
}
svg line.messageLine0, svg line.messageLine1 {
  stroke: var(--darkreader-neutral-text) !important;
}
div.mermaid .actor {
  fill: var(--darkreader-neutral-background) !important;
}
embed[type="application/pdf"][src="about:blank"] { filter: invert(100%) contrast(90%); }</style></head>
  <body>
    <header>
    <h1>Guess the Doggo</h1>
    <p>What breed is the dog in this image?</p>

    </header>

    <main>
    <div id="image-frame">
    </div>
    <div id="options">
    </div>

    </main>

  


  <script type="module">

    const RANDOM_IMG_ENDPOINT = "https://dog.ceo/api/breeds/image/random";

    const BREEDS = ["affenpinscher", "african", "airedale", "akita", "appenzeller", "shepherd australian", "basenji", "beagle", "bluetick", "borzoi", "bouvier", "boxer", "brabancon", "briard", "norwegian buhund", "boston bulldog", "english bulldog", "french bulldog", "staffordshire bullterrier", "australian cattledog", "chihuahua", "chow", "clumber", "cockapoo", "border collie", "coonhound", "cardigan corgi", "cotondetulear", "dachshund", "dalmatian", "great dane", "scottish deerhound", "dhole", "dingo", "doberman", "norwegian elkhound", "entlebucher", "eskimo", "lapphund finnish", "bichon frise", "germanshepherd", "italian greyhound", "groenendael", "havanese", "afghan hound", "basset hound", "blood hound", "english hound", "ibizan hound", "plott hound", "walker hound", "husky", "keeshond", "kelpie", "komondor", "kuvasz", "labradoodle", "labrador", "leonberg", "lhasa", "malamute", "malinois", "maltese", "bull mastiff", "english mastiff", "tibetan mastiff", "mexicanhairless", "mix", "bernese mountain", "swiss mountain", "newfoundland", "otterhound", "caucasian ovcharka", "papillon", "pekinese", "pembroke", "miniature pinscher", "pitbull", "german pointer", "germanlonghair pointer", "pomeranian", "medium poodle", "miniature poodle", "standard poodle", "toy poodle", "pug", "puggle", "pyrenees", "redbone", "chesapeake retriever", "curly retriever", "flatcoated retriever", "golden retriever", "rhodesian ridgeback", "rottweiler", "saluki", "samoyed", "schipperke", "giant schnauzer", "miniature schnauzer", "english setter", "gordon setter", "irish setter", "sharpei", "english sheepdog", "shetland sheepdog", "shiba", "shihtzu", "blenheim spaniel", "brittany spaniel", "cocker spaniel", "irish spaniel", "japanese spaniel", "sussex spaniel", "welsh spaniel", "english springer", "stbernard", "american terrier", "australian terrier", "bedlington terrier", "border terrier", "cairn terrier", "dandie terrier", "fox terrier", "irish terrier", "kerryblue terrier", "lakeland terrier", "norfolk terrier", "norwich terrier", "patterdale terrier", "russell terrier", "scottish terrier", "sealyham terrier", "silky terrier", "tibetan terrier", "toy terrier", "welsh terrier", "westhighland terrier", "wheaten terrier", "yorkshire terrier", "tervuren", "vizsla", "spanish waterdog", "weimaraner", "whippet", "irish wolfhound"];

    
    // Utility function to get a randomly selected item from an array
    function getRandomElement(array) {
        const i = Math.floor(Math.random() * array.length);
        return array[i];
    }

    // Utility function to shuffle the order of items in an array in-place
    function shuffleArray(array) {
        return array.sort((a,b) => Math.random() - 0.5);
    }



    // TODO 1
    // Given an array of possible answers, a correct answer value, and a number of choices to get,
    // return a list of that many choices, including the correct answer and others from the array
    function getMultipleChoices(n, correctAnswer, array) {
        // Use a while loop and the getRandomElement() function
        // Make sure there are no duplicates in the array
        const choices = [];

        choices.push(correctAnswer);
        while(choices.length <n)
        {
          let candidate = getRandomElement(array);
          if(!choices.includes(candidate))
          {
            choices.push(candidate);
          }
        }
        return shuffleArray(choices);
    }

    
    // TODO 2
    // Given a URL such as "https://images.dog.ceo/breeds/poodle-standard/n02113799_2280.jpg"
    // return the breed name string as formatted in the breed list, e.g. "standard poodle"
    function getBreedFromURL(url) {
        // The string method .split(char) may come in handy
        // Try to use destructuring as much as you can
        let unspliteBreed = url.split('/')[4];
        let [brd,sbrd] = unspliteBreed.split('-');
        return [sbrd,brd].join("").trim();
    }



    // TODO 3
    // Given a URL, fetch the resource at that URL, 
    // then parse the response as a JSON object,
    // finally return the "message" property of its body
    async function fetchMessage(url) {
      const response = await fetch(url);
      const body = await response.json();
      const  {message} = body; 
      return message;
    }


    // Function to add the multiple-choice buttons to the page
    function renderButtons(choicesArray, correctAnswer) {

        // Event handler function to compare the clicked button's value to correctAnswer
        // and add "correct"/"incorrect" classes to the buttons as appropriate
        function buttonHandler(e) {
            if (e.target.value === correctAnswer) {
                e.target.classList.add("correct");
            } else {
                e.target.classList.add("incorrect");
                document.querySelector(`button[value="${correctAnswer}"]`).classList.add("correct");
            }
        }

        const options = document.getElementById("options"); // Container for the multiple-choice buttons

        // TODO 4
        // For each of the choices in choicesArray,
        // Create a button element whose name, value, and textContent properties are the value of that choice,
        // attach a "click" event listener with the buttonHandler function,
        // and append the button as a child of the options element

        for(let choice of choicesArray) {
          const button = document.createElement("button");
          button.textContent = choice;
          button.value = choice;
          button.name = choice;
          button.addEventListener("click",buttonHandler);
          options.appendChild(button);
        }
        
    }


    // Function to add the quiz content to the page
    function renderQuiz(imgUrl, correctAnswer, choices) {
        const image = document.createElement("img");
        image.setAttribute("src", imgUrl);
        const frame = document.getElementById("image-frame");

        image.addEventListener("load", () => {
            // Wait until the image has finished loading before trying to add elements to the page
            frame.replaceChildren(image);
            renderButtons(choices, correctAnswer);
        })
        
    }

    // Function to load the data needed to display the quiz
    async function loadQuizData() {
        document.getElementById("image-frame").textContent = "Fetching doggo...";
        
        const doggoImgUrl = await fetchMessage(RANDOM_IMG_ENDPOINT);
        const correctBreed = getBreedFromURL(doggoImgUrl);
        const breedChoices = getMultipleChoices(3, correctBreed, BREEDS);

        return [doggoImgUrl, correctBreed, breedChoices];
    }

    // TODO 5
    // Asynchronously call the loadQuizData() function,     
    // Then call renderQuiz() with the returned imageUrl, correctAnswer, and choices 
    
    const [doggoImgUrl,correctBreed,breedChoices] = await loadQuizData();
    console.log(doggoImgUrl);
    renderQuiz(doggoImgUrl,correctBreed,breedChoices);


  </script>

</body></html>
```

## Coding Exercise provided by the GSG Team

### [Build a Rick & Morty characters list](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)

