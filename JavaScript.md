# JavaScript

1. Objects & properties : Characteristic of the current webpage
2. Events : what has happen when user click or tap
3. Methods : a) tell something about the object; b) change value of the objects properties

## The Browser Object Model  :
### Property
window.innerHeight
window.innerWidth
window.pageXOffset
window.pageYOffset
window.screenX
window.screenY
window.location
window.document
window.history
window.history.lenght
window.screen
window.screen.width
window.screen.height
### Method
window.alert()
window.open()
window.print()


## Document Object Model (DOM)
### Property
document.title
document.lastModified
document.URL
document.domain
### Metod
document.write()
document.getElementById()
document.querySelectorAll()
document.createElement()
document.createTextNode()

## Global Objects :
### Property
length
### Method
### String Object
toUpperCase()
toLowerCase()
charAt()
indexOf()
lastIndexOf()
subString()
split()
trim()
replace()
#### Number Object
isNaN()
toFixed() : fix decimal
toPrecision() : be precision 3 digit if (3)
toExponential()
#### Math Object
Math.PI
Math.round()
Math.sqrt(n) :square root of positive number
Math.ceil() : Round up to nearest integer
Math.floor() : Round down to nearest integer
Math.random()
sin()
cos()
tan()
###Date Object and time
getDate() / setDate() : day of the month
getDay() : day of the week (0-6)
getFullYear() / setFullYear() : year (4 digits)
getHours()  / setHours() : hour(0-23)
getMilliseconds() / setMilliseconds() (0-999)
getMinutes() / setMinutes() : (0-59)
getMonth() / setMonth() : (0-11)
getSeconds() / setSecond() : (0-59)
getTime() / setTime() : yu--[=[][0-6y\]]
getTimezoneOffset()
toDateString()
toTimeString()
toString()


innerHTML
textContent
document.write()

## Switch Statement

switch(level) {
  case 1:
  title = 'Level 1';
  break;

  case 2:
  title = 'Level 2';
  break;

  case 3:
  title : 'Level 3';
  break;

  default:
  title = 'Test';
  break
}   

## Wroking with DOM

### Access Elements
* Select Individual Element Node
getElementById()
querySelector() : use a CSS selector and return first matching element  Example: querySelector('css selector')

* Select Multiple Element Node
getElementsByClassName()
getElementsByTagName()
querySelectorAll() : use a CSS selector and return ALL matching element  Example: querySelector('css selector')

* Traversing bet elements node
parentNode
previousSibling / nextSibling
firstChild / lastChild

### Work with elements
* Access/update text node
nodeValue
* Work with html content
innderHTML
textContent
createElement()
createTextNode()
appendChild() / removeChild()
* Access or Update Attribute Values
className / id
hasAttribute()
getAttribute()
setAttribute()
removeAttribute()

item() : return individual node from Nodelist
### Example :
firstItem = elements.item(0);
firstItem = elements[0];




## Callback Interlude
* Make sure the functions run in correct sequence as you required.
```
const do_first_and_second = function ( callback ) {
    setTimeout(function () {
        console.log( "Do First." );
        callback();
    }, 1000);
}

const do_second = function () {
    console.log( "Do Second." );
}

do_first_and_second( do_second );

// => "Do First."
// => "Do Second."
```


## AJAX (Asynchronous JavaScript and XML)
* let's applications send and retrieve data from server asynchronously. (that a page can be loaded/updated without interfering with the display and behaviour of the 'current' page, and without requiring the page to be reloaded.)
* Basic approach
  - Create an instance of the XMLHttpRequest object.
  - Open a HTTP request (on the instance).
  - Send the Request (on the instance).
  ```
  // 1. Create an instance of the XMLHttpRequest object
  const xhr = new XMLHttpRequest();
  // 2. Open an HTTP request, in the format below:
  //    xhr.open(HTTP VERB, PATH/URL)
  xhr.open( "GET", "http://www.some-website.com/some-path" );
  // 3. Send the request.
  xhr.send();
  ```

## AJAX wtih jQuery

* Basic usage
```
// Basic syntax:
$.ajax( url, { OPTIONS } );
// Example:
$.ajax( "/stats", { method: "GET" } );

// Preferred syntax:
$.ajax({ OPTIONS });
// Preferred syntax example:
$.ajax({
  url: '/post',
  type: 'GET',
  // etc
})
```

* Complex Example
```
// Using the core $.ajax() method
$.ajax({

    // The URL for the request
    url: "/post",

    // The data to send (will be converted to a query string)
    data: {
        id: 123
    },

    // The type of request
    type: "GET",

    // The type of data we expect back
    dataType : "json",

    // Code to run if the request succeeds.
    // The responseText is passed to the 'success' function as the 'data' argument
    success: function( data ) {
        $( "<h1>" ).text( data.title ).appendTo( "body" );
        $( "<div class=\"content\">").html( data.html ).appendTo( "body" );
    },

    // Code to run if the request fails.
    // The request, the status code of the request and the error thrown are passed to the 'error' function as arguments
    error: function( xhr, status, errorThrown ) {
        alert( "Sorry, there was a problem!" );
        console.log( "Error: " + errorThrown );
        console.log( "Status: " + status );
        console.dir( xhr );
    },

    // Code to run when the request is completed, regardless of success or failure
    complete: function( xhr, status ) {
        console.log( "The request is complete." );
    }

});

```

## Map function
var array = [1,2,3];
array.Map => function map() {[native code]}
array.map(function(number)) { return number * 2};
result => [2, 4, 6]
array.map(function(number) { return '<div>' + number '</div>'});
result => ["<div>1</div>", "<div>2</div>", "<div>3</div>"]


## Property
Object.defineProperty
.hasOwnProperty('xxx')


## Prototype
### Function Prototype
* Prototype is an object, not a class
    Object instance, become prototype for all objects created using constrcutor 
### Object Prototype
* Object does not prototype property
* Object prototype : object intance which the object is inherited
```
var fluffy = new Cat('Fluffy', 'White')
display(fluffy.__proto__)
```

## Arrays
* `.some()` => if any of the array include 
* `.every()` => every items in the array include
* `.find()` => something like filter but show you the first item it finds
* `.findIndex()` => find index of the array
* `.slice(3)` => keep items in an array from index number 3 onwards
* `.slice(2, 4)` => keep items in an array from index 2 to index 3. Index 4 is
  removed.

*`.splice(1, 0, 'Feb')` => inserts at 1st index position, 1 start index of
array, replace element 0 (in this case nothing to replace), add in 'Feb' to that
position
* `.splice(4, 1, 'May')` => replace 1 element at 4th index.

Eg:
```
    const comment = comments.find( function(comment) {
      if (comment.id === 823423) {
        return true;
      }
    });
OR
    const comment1 = comments.find(comment => comment.id === 823423)

    const index = comments.findIndex( comment => comment.id === 823423)
    const remove = comments.splice(index, 1)
```

* `Math.abs(x)` => convert number into abolute number ( -ve to positive)
* `.toString()` => convert numbers to string 
* `Number('test')` => convert string to number
* `split('test')` => convert data into array and slipt by empty '' = [t,e,s,t]
* `str.split('')`
* `str.join('')`
* `str.reverse()`
* `array.sort()`
* `charAt(3)` => charactor index of the string 
* `Math.abs(value)`
* `sum.map(Number)` = map is interate what's inside sum and put a function in
  the ()
* `reduce(function(a,b) {return a + b}, 0)`
* `arry.slice(2, 4)` => slice and array, start with index 2 and cut of index
  incliding 4

### Object

Create new Object
`const newObject = new Object();`

```
const favouriteCar = {
  manufacturer: "Jaguar",
  year: 1963,
  model: "E-Type"
}

// Dot notation access to object properties
favouriteCar.year

// Square bracket notation access to object properties
favouriteCar["year"]
```


```
const obj = {
  a: 1,
  b: 2,
  c: 3
};

for (let prop in obj) {
  console.log( "o." + prop + " = " + obj[prop] );
}
```
return prop = a, b, c; obj[prop] = 1, 2, 3


### add object into an array

  accounts: [
    { sherine: 8000 }
  ],
  addAcct: (name, balance) => {
    temp = {};
    temp[name] = balance;
    bank.accounts.push(temp);
    return bank.accounts;
  },

`forEach()` => method loop through the array and applies the same function to
every tems in it
```
var result = [];
people.forEach(function(person) {
    if (person.rate >= 65 && person.rate <= 90 ) {
      result.push(person)
    }
  // Loop through results array & add people to results table
})
```
`filter()` => method applies the same fucntion to each itme in the array, but
that function return only ture or flase. If return tru, the filter() method adds
that item to a new array
```
function priceRange(person) {
  return (person.rate >= 65) && (person.rate <= 90);
}
var result = [];
results = people.filter(priceRange) // filter calls priceRange()
// Loop through results array & add matching people to results table
```

`trim()` => remove white space
