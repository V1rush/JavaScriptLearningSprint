# Day 4: Events & Handlers, Conditionals, Map & Filters and Doggos Quiz Game
The following README file offers a concise overview of the JavaScript lessons covering Event Handlers, Conditionals, and the usage of Map and Filter functions. Within these lessons, we explore the process of implementing event handlers, understanding conditional statements, as well as the application of Map and Filter functions in JavaScript. These lessons provide a comprehensive understanding of working with event handling, making decisions based on conditions, and leveraging the power of Map and Filter functions for data manipulation.

## Lesson 1: << Events & Handlers >>

Events are actions that happen within a webpage or to be precise the DOM, they can be either triggered by the user himself or by the browser. here are the key points of what we've covered

- The web browser fires something we call events when certain things happen on the page. for example when the user clicks somewhere on the page, a click event is fired
- to catch evetns and make use of them we must make an event listener, we can make such thing using this method `.addEventListener` which is used to attach an event listener to a specific element on a web page.
- This method takes two parameters. The first parameter is the name of the event, and the second parameter is a callback function or a handler function that can receive the event itself.
- The event is an object that provides information about the event that just occured.
- Different kinds of events =>`click`, `dblclick`, `mouseover`, `mouseout` and lots more


## Lesson 2: << Conditionals >>

Conditionals in programming execute code blocks based on conditions, enabling decision-making and flow control in a program. They rely on evaluating conditions as true or false to determine which code path to follow.

- we can use `if`, `else if` and `else` structure to perform certain lines of code depending on a certain boolean expression evaluation.
- we have other logical operator such as the logical `AND` which is represented in JavaScript as `&&` which represents the conjunction between two conditons, meaning both conditions must be satisfied in order to get the value `true`.
- Another logical operator is the logical `OR` which is represented as `||` which represents a logical disjunction between two conditions. meaning that the epxression evaluates to `true` if atleast one of its operands is evaluated to `true`
- empty arrays and objects are truthy but empty strings are falsy, null is falsy as well as undefnined.


## Lesson 3: << Map, Filter and Spread >>

The `map` and `filter` are builtin array methods which are pretty much very useful methods to use while coding in the manner of manipulating arrays, here are some points coverd.

- The `map` method allows you to iterate over each element of an array and modify or manipulate each element based on a given callback function, it returns the new array after it is done.
- The `filter` method allows you to create a new array containing only the elements that pass a certain condition or criteria defined by a callback function. it returns a shallow copy of the new array.
- Spread is an operator that is used to insert an array A to another array B, so A becomes a subarray of B. it is represented as `...` in JavaScript.

## Lesson 4: Doggos Quiz Game
this projects is a website that shows a picture of a dig and we're to guess its breed.
I will go into further details involving the implementation and other information in tomorrow's document.

## Code Examples

### < Events & Handlers >

```javascript
//Code sample.
const statement = document.getElementById("statement");

const optionButtons = document.querySelectorAll("#options")[0].children
const firstButton = optionButtons[0]; // assigning a button to firstButton variable.
firstButton.addEventListener("click",event => { //his line attaches an event listener to the firstButton element. It listens for a "click" event on that button. When the button is clicked
console.log(event.target); // afterwards this is printed. this callback function can be called as many time as the user clicks on the button.
});
```

### < Conditionals > 

```javascript
//Code sample.
let a = 10;
if(a) { // any number evaluates to true.
console.log("printed"); // output: printed
if(a-10){
console.log("printed");
}
else {
console.log("printedn't :)") // you know the output lol
}
if([])
{
console.log("works"); // prints : works
}
```

### < Map & Filter >

```javascript
const arr = [1,2,3,4,5];

//map
const addNum = arr.map(iterator=> iterator+10);
console.log(addNum); //outputs [11,12,13,14,15]
console.log(arr); //outputs [1,2,3,4,5] -> it does not mutate the original array.

//filter
const oddNumArr = arr.filter(iteraor => iterator&1);
console.log(oddNumArr); //outputs [1,3,5];
console.log(arr); outputs [1,2,3,4,5]

//spread

arr.push(...addNum);
console.log(arr); // outputs [1,2,3,4,5,11,12,13,14,15]

const newarr = [...arr,..arr];
console.log(newarr); //outputs [1,2,3,4,5,11,12,13,14,15,1,2,3,4,5,11,12,13,14,15]
```

## Completed quiz project code

```javascript

<div id="torrent-scanner-popup" style="display: none;"><template shadowrootmode="open"><link rel="stylesheet" href="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/css/custom.css"><div id="yf-bt-wrapper" class="free"><div class="header"><img class="sts-logo" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/ts-free-logo.png"><div class="search-content"><input id="search-input" class="search-input" type="search" placeholder="Start your search here..."><span id="search-btn" class="search-btn"></span></div></div><div class="container"><div class="main-container"><div id="torrent-data" class="torrent-content"><div class="t-table"><div class="t-header"><div class="t-name">Torrent search results</div></div><div id="checked-sites" class="checked-sites-section"><div class="left">Checked Sites</div><div class="right"><span id="sites-count" class="sites-count">0</span></div></div><div id="table-body" class="t-body"><div id="loading" class="spinner"><div class="bounce1"></div><div class="bounce2"></div><div class="bounce3"></div></div><div class="table-message-container" id="table-message"><p>No items to list <br> Use the search bar above for instant results</p></div></div></div></div><div class="tooltip"><p class="tooltip-text">To see search results, type here and hit `Enter`</p></div><div class="footer"><span><span id="numberScanned" class="numberScanned">No results</span></span></div><div class="upgradeProPanel"><div class="upgradeProPanelTitle">Try our Pro Versions to unlock:</div><div class="upgradeProPanelList"><div><p>Faster Results</p></div><div><p>Secure Torrenting</p></div><div><p>Unlimited Search Results with detailed torrent info</p></div><div><p>1-YR Subscription to CyberGhost VPN <span style="font-size:8px;">(PRO+VPN only)</span></p></div></div><a class="upgrade-to-pro-button-2" id="buy-pro-vpn" href="https://www.utorrent.com/webpro-offer/?utm_source=Lavasoft&amp;utm_medium=version_1.0&amp;utm_campaign=Scanner" target="_blank">BUY PRO + VPN</a><a class="upgrade-to-pro-button-2" id="buy-pro" href="https://www.utorrent.com/webpro-offer/?utm_source=Lavasoft&amp;utm_medium=version_1.0&amp;utm_campaign=Scanner" target="_blank">BUY PRO</a></div></div><div class="sync-container nav-se-container"><div class="nav-se-content"><img class="sync-icon nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-sync.svg"><div class="nav-se-title">One more step to go before you start torrenting!</div><p class="nav-se-text">This extension can sync results with BitTorrent and/or uTorrent for instant downloading.</p><p class="nav-se-text">To activate this feature, please click on the button below, and then on the Chrome message to activate the 'Messaging Permission'.</p><button class="sync-permission-btn nav-se-btn">Activate Messaging Permission</button></div><div class="nav-se-content display-none"><img class="sync-icon nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-sync.svg"><div class="nav-se-title">Syncing...</div><p class="nav-se-text">Please allow Messaging Permissions in the proceeding Chrome message.</p></div><div class="nav-se-content display-none"><img class="sync-icon nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-success.svg"><div class="nav-se-title">Sync Complete</div><p class="nav-se-text">You have successfully activated the “Messaging Permission” feature. All your search results will sync with BitTorrent and/or uTorrent.</p></div></div><div class="license-container nav-se-container"><div class="nav-se-content"><img class="nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-key2.svg"><div class="nav-se-title">Enter License Key</div><p class="nav-se-text">Enter your license key and click on the activate button to start using <span>µTorrent Web Pro.</span></p><input type="text" id="license-input-key" class="license-input-key" placeholder="Enter Key"><div class="license-spinner"><div class="bounce1"></div><div class="bounce2"></div><div class="bounce3"></div></div><button id="license-activate-button" class="license-activate-button nav-se-btn">Activate</button><p>Don't have a license key? <a class="license-buy-link" target="_blank">Click here</a></p></div><div class="nav-se-content display-none"><img class="nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-success.svg"><div class="nav-se-title">Happy Torrenting!</div><p class="nav-se-text">You are now an active PRO user</p><p class="nav-se-text">Your key is valid until <span class="expiry-date"></span></p></div><div class="nav-se-content display-none"><img class="nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-alert.svg"><div class="nav-se-title">Your license key has expired</div><p class="nav-se-text">Looks like your license key has expired, to renew your PRO license key, please select a license type:</p><a class="upgrade-to-pro-button-2 buy-license-expiry-button" href="https://www.utorrent.com/webpro-offer/?utm_source=Lavasoft&amp;utm_medium=version_1.0&amp;utm_campaign=Scanner" target="_blank">Buy Pro + VPN</a><a class="upgrade-to-pro-button-2 buy-license-expiry-button" href="https://www.utorrent.com/webpro-offer/?utm_source=Lavasoft&amp;utm_medium=version_1.0&amp;utm_campaign=Scanner" target="_blank">Buy Pro</a><p class="nav-se-text">Already have a license key? <a class="link" id="show-license-panel">Click here</a></p></div><div class="nav-se-content display-none"><img class="nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-success.svg"><div class="nav-se-title">Pro User</div><p class="nav-se-text">Your key is valid until <span class="expiry-date"></span></p><p class="nav-se-text">Your License Key:</p><p class="nav-se-text"></p><p class="nav-se-text margin-top-50">Switch back to Torrent Scanner Free?</p><button class="activate-free-btn nav-se-btn">Revert to Free Version</button></div></div><div class="feedback-container nav-se-container"><div class="nav-se-content"><img class="nav-se-icon" src="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/img/assets/icon-feedback.svg"><div class="nav-se-title">Feedback</div><p class="nav-se-text">Help us improve Torrent Scanner, send us comments, bugs, feedback, and suggestions.</p><button id="feedback-button" class="feedback-button nav-se-btn">Send Feedback</button></div></div><div class="settings-container nav-se-container"><div class="nav-se-content"><div class="settings-title">Settings</div></div><div class="s-table"><div class="s-row"><div class="s-title">FAQ<div class="s-arrow"><span class="arrow-down"></span></div></div><div class="s-content faq-content"><p class="faq-text">FAQ: <a href="chrome-extension://aegnopegbbhjeeiganiajffnalhlkkjb/faq.html" target="_blank">Click here</a></p></div></div><div class="s-row"><div class="s-title">Rate the extension<div class="s-arrow"><span class="arrow-down"></span></div></div><div class="s-content"><p class="rate-text">How did you like the extension experience?</p><div class="rating"><span class="rating-star">★</span><span class="rating-star">★</span><span class="rating-star">★</span><span class="rating-star">★</span><span class="rating-star">★</span></div><button class="rating-btn nav-se-btn" disabled="">Submit</button></div></div><div class="s-row"><div class="s-title">About<div class="s-arrow"><span class="arrow-down"></span></div></div><div class="s-content about-content"><div class="about-version">Version 1.3.0 <br><br> What's New</div><div class="about-new"><p></p><ul><li>Experience a complete new User Interface of the extension. It is enhanced and user friendly now.</li><li>Squashed some bugs.</li></ul><p></p></div></div></div><div class="s-row"><div class="s-title">Privacy Policy<div class="s-arrow"><span class="arrow-down"></span></div></div><div class="s-content"><div class="policy-text">Adaware Software (7270356 Canada Inc.) is the operator of the Adaware products suites and related services (the “<b>Company</b>”, ”<b>we</b>” or “<b>us</b>”). We respect your privacy rights and we are committed to protecting them. This privacy policy (“<b>Privacy Policy</b>” or simply “<b>policy</b>”) governs our products, services and websites that link to this Privacy Policy, and describes our practices of processing data from you. By “<b>you</b>”, we refer to either or all of the following: (i) visitors to our websites that links to this Privacy Policy (“<b>Visitor</b>” and “<b>Website</b>”, respectively); (ii) our customers using our software products and Services (“<b>User</b>”); and (c) a business customer, a business partner that has a contractual relationship with us or a prospective customer that is yet to be engaged in a contract with us (“Business Customer”). Unless explicitly mentioned otherwise, the information in this Privacy Policy refers to any and all data subject types (“you” or “your’). <br><br> For the purpose of this policy, the “<b>Service(s)</b>” shall include any software licensed by the Company, including features offered by or within the installed software or additional software scripts available therein (either downloaded from one of our websites, pre-installed on your device, downloaded through a third party website, obtained on a physical medium, or otherwise), or services provided through and/or on top such software, services offered on our websites, communication forums, support services, account operation, updates, enhancements, new features, premium support, extended guarantees, online version and free versions of a software or additional services or features as we ay make available from time to time. <br><br> If you are a California resident, please also see our <a href="https://www.adaware.com/CCPA/" target="_blank">CCPA Notice</a>. <br><br> <a href="https://www.adaware.com/privacy-policy/" target="_blank">Read more</a></div></div></div><div class="s-row" style="display: none;"><div class="s-title">Contact Us<div class="s-arrow"><span class="arrow-down"></span></div></div><div class="s-content"><div class="contact-text">For any payment and order-related support, please contact us at Email: <a href="mailto:support@torrentscanner.zendesk.com">support@torrentscanner.zendesk.com</a> or <a href="mailto:pcsoftwareinfo.com">pcsoftwareinfo.com</a><br><br>Phone: <a href="https://pcsoftwareinfo.com/contact.aspx" target="_blank">Click here</a></div></div></div></div></div></div><div class="nav"><button id="btnSync" class="nav-btn">Sync</button><button id="btnLicense" class="nav-btn">License</button><button id="btnHome" class="nav-btn">Home</button><button id="btnFeedback" class="nav-btn">Feedback</button><button id="btnSettings" class="nav-btn">Settings</button></div></div></template></div></body></html>
<!DOCTYPE html>
<!-- saved from url=(0063)https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html -->
<html lang="en-US">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />

    <title>Quiz.js</title>
    <style>
      body {
        margin: 1rem auto;
        padding: 3rem;
        font-family: sans-serif;
      }
      header {
        width: 50%;
        margin: 1em auto;
      }
      main {
        min-width: 25rem;
        max-width: 50%;
        margin: 0px auto;
        display: flex;
        flex-direction: column;
      }
      #statement {
        border: 1px solid black;
        border-radius: 0.5rem;
        box-shadow: 5px 5px 5px gray;
        padding: 1rem;
        font-size: x-large;
        text-align: center;
        margin: 1rem 0px;
        min-height: 2em;
      }
      #explanation {
        padding: 1rem;
        text-align: center;
      }
      #options {
        width: 100%;
        display: flex;
        flex-direction: column;
      }
      button {
        padding: 0.5rem;
        font-size: medium;
        border-radius: 5px;
      }
      button:hover {
        background-color: bisque;
      }
      .correct {
        background-color: lightgreen;
      }
      .incorrect {
        background-color: lightpink;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Quiz.js</h1>
      <p>Do you know JS? Find out!</p>
    </header>

    <main>
      <div id="statement"></div>

      <div id="options">
        <button name="true" value="true">true</button>
        <button name="false" value="false">false</button>
      </div>

      <div id="explanation"></div>
    </main>

    <script type="text/javascript">
    // TODO 1: Declare & assign variables pointing to the corresponding element(s)
    // statement should be the "statement" div
    const statement = document.getElementById("statement");
    // optionButtons should be all the elements within the "options" div
    const optionButtons = document.querySelectorAll("#options")[0].children;
    // explanation should be the "explanation" div
    const explanation = document.getElementById("explanation");


    // TODO 2: Declare & assign a variable called fact
    // Its value should be an object with a statement, true/false answer, and explanation 
    const fact = {
      statement: "Arrays are just like objects",
      answer : true,
      explanation : "Change my mind",
    }; 

    
    // TODO 3: Set the text of the statement element to the fact's statement
        statement.textContent = fact["statement"];


    // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
    // disable(button) should set the button element's attribute "disabled" to the value ""
    const disable = (button) => button.setAttribute("disabled","true"); 
    // enable(button) should remove the attribute "disabled" from the button element
    const enable = button => button.removeAttribute("disabled");



    // TODO 5: Declare an isCorrect function that compares a guess to the right answer
    // isCorrect(guess) should return true if the guess matches the fact's answer
    const isCorrect = guess => { 
      return guess === fact.answer;
    }
    const inCorrect2= guess => {
      return guess === "true" ? "correct" : "incorrect";
    }


    // TODO 6A: Use a for loop to add a click event listener to each of the optionButtons
    for(let o of optionButtons) {
      o.addEventListener("click",event=>{
        // TODO 6B: Within the event handler function, display the fact's explanation by setting the text of the explanation element
        explanation.textContent = fact.explanation;
        
        // TODO 7: Within the event handler function, 
        // Use a for loop to disable all the option buttons
        if(event.target == o)
          for(let x of optionButtons)
              disable(x);
        
        // TODO 8: Within the event handler function,
        // Get the guessed value from the clicked button
        // Use a conditional to compare the guess to the fact's answer
        // and add the "correct"/"incorrect" class as appropriate
         
        o.classList.add(inCorrect2(o.value));
      });
    }
    </script>
  </body>
</html>
```

## Code Exercises provided by GSG Team

### [Exercise: Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)

```javascript
function checkSign(num) {
  return (num > 0) ? "positive" : (num === 0) ? "zero" : "negative";
}

checkSign(10);
```

### [Exercise: Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)

```javascript
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line
let ans;
if(strokes === 1)
  ans = "Hole-in-one!";
else if(strokes <= par-2)
  ans = "Eagle";
else if(strokes === par-1)
  ans = "Birdie";
else if(strokes === par)
  ans = "Par"
else if(strokes === par + 1)
  ans = "Bogey";
else if(strokes === par+2)
  ans = "Double Bogey";
else if(strokes >= par +3)
  ans = "Go Home!";

  return ans;
  // Only change code above this line
}

golfScore(5, 4);
```
### [Exercise: Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)

```javascript
// The global variable
const watchList = [
  {
    "Title": "Inception",
    "Year": "2010",
    "Rated": "PG-13",
    "Released": "16 Jul 2010",
    "Runtime": "148 min",
    "Genre": "Action, Adventure, Crime",
    "Director": "Christopher Nolan",
    "Writer": "Christopher Nolan",
    "Actors": "Leonardo DiCaprio, Joseph Gordon-Levitt, Elliot Page, Tom Hardy",
    "Plot": "A thief, who steals corporate secrets through use of dream-sharing technology, is given the inverse task of planting an idea into the mind of a CEO.",
    "Language": "English, Japanese, French",
    "Country": "USA, UK",
    "Awards": "Won 4 Oscars. Another 143 wins & 198 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMjAxMzY3NjcxNF5BMl5BanBnXkFtZTcwNTI5OTM0Mw@@._V1_SX300.jpg",
    "Metascore": "74",
    "imdbRating": "8.8",
    "imdbVotes": "1,446,708",
    "imdbID": "tt1375666",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Interstellar",
    "Year": "2014",
    "Rated": "PG-13",
    "Released": "07 Nov 2014",
    "Runtime": "169 min",
    "Genre": "Adventure, Drama, Sci-Fi",
    "Director": "Christopher Nolan",
    "Writer": "Jonathan Nolan, Christopher Nolan",
    "Actors": "Ellen Burstyn, Matthew McConaughey, Mackenzie Foy, John Lithgow",
    "Plot": "A team of explorers travel through a wormhole in space in an attempt to ensure humanity's survival.",
    "Language": "English",
    "Country": "USA, UK",
    "Awards": "Won 1 Oscar. Another 39 wins & 132 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMjIxNTU4MzY4MF5BMl5BanBnXkFtZTgwMzM4ODI3MjE@._V1_SX300.jpg",
    "Metascore": "74",
    "imdbRating": "8.6",
    "imdbVotes": "910,366",
    "imdbID": "tt0816692",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "The Dark Knight",
    "Year": "2008",
    "Rated": "PG-13",
    "Released": "18 Jul 2008",
    "Runtime": "152 min",
    "Genre": "Action, Adventure, Crime",
    "Director": "Christopher Nolan",
    "Writer": "Jonathan Nolan (screenplay), Christopher Nolan (screenplay), Christopher Nolan (story), David S. Goyer (story), Bob Kane (characters)",
    "Actors": "Christian Bale, Heath Ledger, Aaron Eckhart, Michael Caine",
    "Plot": "When the menace known as the Joker wreaks havoc and chaos on the people of Gotham, the caped crusader must come to terms with one of the greatest psychological tests of his ability to fight injustice.",
    "Language": "English, Mandarin",
    "Country": "USA, UK",
    "Awards": "Won 2 Oscars. Another 146 wins & 142 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMTMxNTMwODM0NF5BMl5BanBnXkFtZTcwODAyMTk2Mw@@._V1_SX300.jpg",
    "Metascore": "82",
    "imdbRating": "9.0",
    "imdbVotes": "1,652,832",
    "imdbID": "tt0468569",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Batman Begins",
    "Year": "2005",
    "Rated": "PG-13",
    "Released": "15 Jun 2005",
    "Runtime": "140 min",
    "Genre": "Action, Adventure",
    "Director": "Christopher Nolan",
    "Writer": "Bob Kane (characters), David S. Goyer (story), Christopher Nolan (screenplay), David S. Goyer (screenplay)",
    "Actors": "Christian Bale, Michael Caine, Liam Neeson, Katie Holmes",
    "Plot": "After training with his mentor, Batman begins his fight to free crime-ridden Gotham City from the corruption that Scarecrow and the League of Shadows have cast upon it.",
    "Language": "English, Urdu, Mandarin",
    "Country": "USA, UK",
    "Awards": "Nominated for 1 Oscar. Another 15 wins & 66 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BNTM3OTc0MzM2OV5BMl5BanBnXkFtZTYwNzUwMTI3._V1_SX300.jpg",
    "Metascore": "70",
    "imdbRating": "8.3",
    "imdbVotes": "972,584",
    "imdbID": "tt0372784",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Avatar",
    "Year": "2009",
    "Rated": "PG-13",
    "Released": "18 Dec 2009",
    "Runtime": "162 min",
    "Genre": "Action, Adventure, Fantasy",
    "Director": "James Cameron",
    "Writer": "James Cameron",
    "Actors": "Sam Worthington, Zoe Saldana, Sigourney Weaver, Stephen Lang",
    "Plot": "A paraplegic marine dispatched to the moon Pandora on a unique mission becomes torn between following his orders and protecting the world he feels is his home.",
    "Language": "English, Spanish",
    "Country": "USA, UK",
    "Awards": "Won 3 Oscars. Another 80 wins & 121 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMTYwOTEwNjAzMl5BMl5BanBnXkFtZTcwODc5MTUwMw@@._V1_SX300.jpg",
    "Metascore": "83",
    "imdbRating": "7.9",
    "imdbVotes": "876,575",
    "imdbID": "tt0499549",
    "Type": "movie",
    "Response": "True"
  }
];

// Only change code below this line


const ratings = watchList.map(iterator => {
  let temp = {
    title: iterator["Title"],
    rating: iterator["imdbRating"],
  }
  return temp;
});

// Only change code above this line

console.log(JSON.stringify(ratings));
```

### [Exercise: Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)

```javascript
// The global variable
const watchList = [
  {
    "Title": "Inception",
    "Year": "2010",
    "Rated": "PG-13",
    "Released": "16 Jul 2010",
    "Runtime": "148 min",
    "Genre": "Action, Adventure, Crime",
    "Director": "Christopher Nolan",
    "Writer": "Christopher Nolan",
    "Actors": "Leonardo DiCaprio, Joseph Gordon-Levitt, Elliot Page, Tom Hardy",
    "Plot": "A thief, who steals corporate secrets through use of dream-sharing technology, is given the inverse task of planting an idea into the mind of a CEO.",
    "Language": "English, Japanese, French",
    "Country": "USA, UK",
    "Awards": "Won 4 Oscars. Another 143 wins & 198 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMjAxMzY3NjcxNF5BMl5BanBnXkFtZTcwNTI5OTM0Mw@@._V1_SX300.jpg",
    "Metascore": "74",
    "imdbRating": "8.8",
    "imdbVotes": "1,446,708",
    "imdbID": "tt1375666",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Interstellar",
    "Year": "2014",
    "Rated": "PG-13",
    "Released": "07 Nov 2014",
    "Runtime": "169 min",
    "Genre": "Adventure, Drama, Sci-Fi",
    "Director": "Christopher Nolan",
    "Writer": "Jonathan Nolan, Christopher Nolan",
    "Actors": "Ellen Burstyn, Matthew McConaughey, Mackenzie Foy, John Lithgow",
    "Plot": "A team of explorers travel through a wormhole in space in an attempt to ensure humanity's survival.",
    "Language": "English",
    "Country": "USA, UK",
    "Awards": "Won 1 Oscar. Another 39 wins & 132 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMjIxNTU4MzY4MF5BMl5BanBnXkFtZTgwMzM4ODI3MjE@._V1_SX300.jpg",
    "Metascore": "74",
    "imdbRating": "8.6",
    "imdbVotes": "910,366",
    "imdbID": "tt0816692",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "The Dark Knight",
    "Year": "2008",
    "Rated": "PG-13",
    "Released": "18 Jul 2008",
    "Runtime": "152 min",
    "Genre": "Action, Adventure, Crime",
    "Director": "Christopher Nolan",
    "Writer": "Jonathan Nolan (screenplay), Christopher Nolan (screenplay), Christopher Nolan (story), David S. Goyer (story), Bob Kane (characters)",
    "Actors": "Christian Bale, Heath Ledger, Aaron Eckhart, Michael Caine",
    "Plot": "When the menace known as the Joker wreaks havoc and chaos on the people of Gotham, the caped crusader must come to terms with one of the greatest psychological tests of his ability to fight injustice.",
    "Language": "English, Mandarin",
    "Country": "USA, UK",
    "Awards": "Won 2 Oscars. Another 146 wins & 142 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMTMxNTMwODM0NF5BMl5BanBnXkFtZTcwODAyMTk2Mw@@._V1_SX300.jpg",
    "Metascore": "82",
    "imdbRating": "9.0",
    "imdbVotes": "1,652,832",
    "imdbID": "tt0468569",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Batman Begins",
    "Year": "2005",
    "Rated": "PG-13",
    "Released": "15 Jun 2005",
    "Runtime": "140 min",
    "Genre": "Action, Adventure",
    "Director": "Christopher Nolan",
    "Writer": "Bob Kane (characters), David S. Goyer (story), Christopher Nolan (screenplay), David S. Goyer (screenplay)",
    "Actors": "Christian Bale, Michael Caine, Liam Neeson, Katie Holmes",
    "Plot": "After training with his mentor, Batman begins his fight to free crime-ridden Gotham City from the corruption that Scarecrow and the League of Shadows have cast upon it.",
    "Language": "English, Urdu, Mandarin",
    "Country": "USA, UK",
    "Awards": "Nominated for 1 Oscar. Another 15 wins & 66 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BNTM3OTc0MzM2OV5BMl5BanBnXkFtZTYwNzUwMTI3._V1_SX300.jpg",
    "Metascore": "70",
    "imdbRating": "8.3",
    "imdbVotes": "972,584",
    "imdbID": "tt0372784",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Avatar",
    "Year": "2009",
    "Rated": "PG-13",
    "Released": "18 Dec 2009",
    "Runtime": "162 min",
    "Genre": "Action, Adventure, Fantasy",
    "Director": "James Cameron",
    "Writer": "James Cameron",
    "Actors": "Sam Worthington, Zoe Saldana, Sigourney Weaver, Stephen Lang",
    "Plot": "A paraplegic marine dispatched to the moon Pandora on a unique mission becomes torn between following his orders and protecting the world he feels is his home.",
    "Language": "English, Spanish",
    "Country": "USA, UK",
    "Awards": "Won 3 Oscars. Another 80 wins & 121 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMTYwOTEwNjAzMl5BMl5BanBnXkFtZTcwODc5MTUwMw@@._V1_SX300.jpg",
    "Metascore": "83",
    "imdbRating": "7.9",
    "imdbVotes": "876,575",
    "imdbID": "tt0499549",
    "Type": "movie",
    "Response": "True"
  }
];

// Only change code below this line


let rating = watchList.map(iterator=> {
  return {title:iterator["Title"],rating:iterator["imdbRating"]};
})
const filteredList = rating.filter(iterator=> iterator.rating>=8);
console.log(filteredList);


// Only change code above this line

console.log(filteredList);
```
