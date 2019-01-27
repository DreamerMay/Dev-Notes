# Basics

## Variables
* Named value / variable name => score; 100 => value; = `asignment operator`
`score = 100`
* Declaration of variable
`var score;`
* Javascript uses `\` backslash to escape character to specify special charaters
`var story = "She looked at me. \"What did you say?\" she asked.";`

## Numbers
* JS uses 64 bits to store single number value
* E as exponent `2.998e8`
* Special numbers - `Infinity` & `-Infinity` => 0 / 0 = `Infinity`
* `NaN` is not a number. Result of a nonsensical computation

## String
* Newline can use ``
* \ within the quoted text, indicate special character (Escaping the character)
* `\n` newline
* `\t` newtab
* `\"\\n\"` will show \n as text
* `+` concatenates => put the string together as a word wihtout space unless
  space were added in between " "
* `` backtick-quoted strings => template literals; `half of 100 is ${100 / 2}`
* `typeof` produce string value naming type of the value. takes only one value.
  `unary operators`. Those takes 2 values `binary operators`

## Boolean 
* true or false

## Comparison
* `<` `>` is less than or greater than. it can compare string as well. Updercase
  always less than loercase.
* Compare from lef to right, comparing the Unicode codes one by one
* ` >=, <=, ==, !=` Only one value is not equal to itself `NaN == NaN => false`

## Locigal operators
* `&&, ||` and, Or. THese 2 have the lower precedence `1 + 1 == 2 && 10 * 10 >
  50` && process last
* `!` Not - flips the value given
* `ternary operator` operating on three values. using ? and : `console.log(true
  ? 1 : 2);` => 1. This is coiditional operator

## Empty Values
* `null`, `undefined ` - absence of meaningful value. Values without info
* `undefined` -> yield some value
* `null` -> 

## Automatic type conversion
* when wrong type of value were given, JS convert value to what it expected or
  want => type coercion
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
* If you do not want to automatic convert, use `===, !==`. Precise equation

## short-circuiting of logical operators
* `||` return to left when it can be convert into true, else left
* 0, NaN and empty string("") => false, so it will not show this first `0 || -1 produces -1, and "" || "!?" yields "!?"`
console.log(null || "user")
// → user
console.log("Agnes" || "user")
// → Agnes
true || X => true // because X were never evaluate
false && X => false // because X were never evaluate

# Programing Structure

## Expression and statments
* fragement of code that procduce a values is claled an `expression`

## binding
* mood = "light"
`var` variable = globally use value and change at anytime
`const` constant = value will not be changed
`let` 

## Binding Names
* Must not start with numbers. can be $ or _ but not other punctuation or
  special char
* words with sepcial meaning (let, ) may not use as binding name.
* reserved words not to use
`break case catch class const continue debugger default
delete do else enum export extends false finally for
function if implements import interface in instanceof let
new package private protected public return static super
switch this throw true try typeof var void while with yield`

## The environment
* collection of binding and their values => `environment`

## Functions
* a piece of program wrapped in a value
* `prompt("Enter Password")`, result of `prompt` is string value
* Executing funciton called `invoking, calling or applying`
* value given to functions are called `arguments`

## Console.log
* output of values
* way to generat output
let x = 30;
console.log("the vaue of x is", x); 
// → the value of x is 30

* the || operator denotes lofical or. It produces true if eigher of the values
  given to it is true. "" empty string is not true
console.log(false || true)
// → true
console.log(false || false)
// → false

## Return values
* `Math.max` takes any amount of the number arguments and gives back the
  greatest. `console.log(4,2)` => 4
* `Math.min`

## Control Flow
### Conditional Execution
* `if` statement
* `Number.isNaN` => return only `true` if the argument it is given is NaN.
* `!Number.isNaN(theNumber)` => unless `theNumber` is not-a-number, do this
* after `if` wrapped with brace ({ and }) is single statment called block.
* `if and else`

### While and Do Loops
* `while` create a loop. `while (number <= 12) {`
* `do` loop is a control structure. Always executes its body at least once, and
  test if it should stop only after the first execution.
do {
  yourName = prompt("Who are you?");
} while (!yourName); #TODO come back to for this 
console.log(yourName);
* this program will force you to enter a name. 
* ! convert value to Boolen type. all strings expect "" convert to true.
* This means the loop continues going round until you provide a non-empty name.

### For loop
`for ( let i = 0; i >= string.length; i++ ) {`
* `i = 0` is the initialize the loop
* `i >= string.length` check the part if it needs to continue
* `i++` updates the state of the lloop after every iteration

### Breaking out a loop 
`break` immddiately jump out of the loop
### Updating binding sccinctly
* `+= ++ -= -- *= /=`

### Switch 
switch (prompt("what is the weather like?")) {
  case "rainy";
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny";
    console.llg("Dress lightly");
    break;
  case "cloudy";
    console.log("Go outside");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}

# FUNCTIONS
* if funciton without `return`, result is `undefined`
const power = function (a, b) {

  return result;
} 

* Global variables define outside the function
* Local variables define within the function

* Function declaration
function power(x) {
  return x * x;
}

* Arrow function
const power = (a, b) => {}
 - if only one parameter, you can ommit {}
 const square1 = (x) => {return x * x}
 const square2 = x => x * x;

 * All example of creating function
 // Define f to hold a function value
const f = function(a) {
  console.log(a + 2);
};

// Declare g to be a function
function g(a, b) {
  return a * b * 3.5;
}

// A less verbose function value
let h = a => a % 3;

* `call stack` where computer stores this context 
* Every time a function is called, current context stored on top of this stack
* When a function returns, it removes the top context form the stack and uses
  that context to continue execution. 
* A stack, in programming, is a data structure that allows you to push values
  into it and pop them out again in teh pppositie order.

### Optional Argument
* JS ignore extra parameter
* missing arguments will show value `undefined`
* Upside of given 2 arguments but missing one, function still works..
function square(x) { return x * x; }
console.log(square(4, true, "hedgehog"));
// → 16
* if argument previously declared and when clal function did not declare it will
  defualt as delared answer


# Data Structure

### Properties 
* Eg .lenght(word.lenght), .max in Math Object (Math.max), .toUpperCase()
* null and undefined have no properties, the rest of values all have
* `.x` to access property; `value.x` fetches the property of value named "x";
* `[x]` to access property; `value[x]` tries to evaluate the expression x and
  uses the result, conerted to a string, as the proeprty name

### Methods
* Properties that contain functions are called `methods` of the value they
  belong to, as in “toUpperCase is a method of a string”.

## Array
* items in an arary are called `elements`;
* `items[1] =  "iceland";` => adding or changing elements based on index 1; can
* `items[items.length]` => add new elements to last item
* push, pop, and join functions available as properties on every array.
*


### Objects
* Name of the properties => keys

* Properties whose names aren't valid binding names or valid numbers have to be
  quoted
let descriptions = {
  work: "Went to work",
  "touched tree": "Touched a tree"
};
* delete an object
let anObject = {left: 1, right: 2};
delete anObject(left);
* accesing property name => `Object.keys`
console.log(Object.keys({x: 0, y: 0, z: 2}));
// → ["x", "y", "z"]
* copy all properties from one object to another =>`Object.assign`
let objectA = {a: 1, b: 2};
Object.assign(objectA, {b: 3, c: 4});
console.log(objectA);
// → {a: 1, b: 3, c: 4}
* changing object value `objectA.a = 3`;
* if property name and value name are the same, we do not have to delare
  `events: events`. just `events`

* `for of loop` => get the value of the array, and only store anything that is
  unique by using obj[i] = true; `for (let i of a) {obj[i] = true;}`
* `for in loop` => get the index of the array
* Example in Array usage; it gets the index of the array 
let list = [4, 5, 6];

for (let i in list) { // it gets the index of the array 
   console.log(i); // "0", "1", "2",
}

for (let i of list) {
   console.log(i); // "4", "5", "6"
}

* Example in Object usaage, it gets the Object.keys
const obj = {  
  a: 1,
  b: 2,
  c: 3,
  d: 4
}

for (let elem in obj) { //  it gets the Object.keys
  console.log(`${elem} = ${obj[elem]}`);
}
// a = 1
// b = 2
// c = 3
// d = 4

* `sort()` => `arr.sort([compareFunction])`
* is no function with compare define, it will sort based on first number. Needs
  to define compare function

arr = A.sort( (a,b) => a-b ); // accending

var numberArray = [40, 1, 5, 200];

numberArray.sort(function(a, b) {
  return a - b;
})
console.log('numberArray:', numericStringArray.join());
console.log('Sorted without a compare function:', numericStringArray.sort());
console.log('Sorted with compareNumbers:', numericStringArray.sort(compareNumbers));
//Sorted without a compare function: (4) [1, 200, 40, 5]
//Sorted with compareNumbers: (4) [1, 5, 40, 200]

* ` new .Set()` = store only unique operators, no duplication. (remove duplicates)
let a = [1,2,3,5,2,1,8]
[... new Set(a)];
// return [1,2,3,5,8]

or let bSet = new Set(a); no in array form


* Add and remove at the end of an array `.push(x)` add into last item; `.pop()`
  remove the last item and return it; `.push(x, y)`
* Add and remove at the begining of an array `unshift(x)` `shift()`
* `indexOf(2)` = search from begining of value 2 in the array; `lastIndexOf(2)`
  => searh from end of array for value 2; return `-1` when item can't be found
console.log([1, 2, 3, 2, 1].indexOf(2));
// → 1
console.log([1, 2, 3, 2, 1].lastIndexOf(2));
// → 3
console.log("coconut".indexOf("u"));
// → 5
console.log("one two three".indexOf("ee"));
// → 11
* `slice(2,4)` take start and end indices and return array between them. last index
  is excluded. 
* arr.slice([begin[, end]])
* Does not change original array
var animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]
console.log("coconuts".slice(4, 7));
// → nut
* `slice()` with empty argument, it just clonning the array;
var str = 'The quick brown fox jumps over the lazy dog.';
console.log(str.slice(31));
// expected output: "the lazy dog."

console.log(str.slice(4, 19));
// expected output: "quick brown fox"

console.log(str.slice(-4));
// expected output: "dog."

console.log(str.slice(-9, -5));
// expected output: "lazy"

* `splice(2)` keep the first 2 item in the array OR remove after index 2;
* The splice() method changes the contents of an array by removing or replacing
  existing elements and/or adding new elements.
* Change original array
* `array.splice(1, 2, "replace", "replace2")` => 1 is start of index array, 2 => range from
  start index, if 0 mean add in "replace" in from of 1; if  
const rainbow = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo',
  'violet'];
rainbow.splice(3);
console.log(rainbow; // ['red', 'orange', 'yellow']


var months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// inserts at 1st index position
console.log(months);
// expected output: Array ['Jan', 'Feb', 'March', 'April', 'June']

months.splice(4, 1, 'May');
// replaces 1 element at 4th index
console.log(months);
// expected output: Array ['Jan', 'Feb', 'March', 'April', 'May']

* `items.forEach(showInfo)` loop throught each item
 player.items.forEach(function (item, i) {
    itemsString += " " + (i + 1) + " " + item + spacer.newLine() ;
  });

var array1 = ['a', 'b', 'c'];
array1.forEach(function(element, i) {
  console.log(element, i);
});

// expected output: "a"
// expected output: "b"
// expected output: "c"

[ 'a', 'b', 'c' ].forEach( function (elem, index) {
    console.log(index + '. ' + elem);
});
// => 0. a
// => 1. b
// => 2. c

* Word count
var tweets = [
  "Education is showing business the way by using technology to share
  ➥ information. How do we do so safely?",
  "Enjoy a free muffin & coffee with Post Plus, our new loyalty club
  ➥ exclusive to subscribers!",
  "We're LIVE on Periscope right now answering all your #pet questions
  ➥ - tweet us yours now!"
  ];
var words = {};
var tweetText = tweets.join(" ");
var tweetWords = tweetText.split(" ");
tweetWords.forEach(function (word) {
                                    words[word] = 0;
                                    });
tweetWords.forEach(function (word) {
                                    words[word] = words[word] + 1;
                                    });
console.log(words);

* `concat()` - combine 2 arrays. if argument is empty, it clonning the array
var array1 = ['a', 'b', 'c'];
var array2 = ['d', 'e', 'f'];

console.log(array1.concat(array2));
// expected output: Array ["a", "b", "c", "d", "e", "f"]

Eg 2
const num1 = [[1]];
const num2 = [2, [3]];

const numbers = num1.concat(num2);

console.log(numbers);
// results in [[1], 2, [3]]

// modify the first element of num1
num1[0].push(4);

console.log(numbers);
// results in [[1, 4], 2, [3]]

* `findIndex()` it finds the first value for which the given fucntion return
  true
* string.indexOf(searchvalue, start)
var str = "Hello world, welcome to the universe.";
var n = str.indexOf("welcome"); // 13

var str = "Hello world, welcome to the universe.";
var n = str.indexOf("e"); // 1

* `.fill()` - fills all the elements of an array from a start index to an end
  index with a stati value. the end index is excluded. Do not change the length
  of array.
var array1 = [1, 2, 3, 4];

// fill with 0 from position 2 until position 4
console.log(array1.fill(0, 2, 4));
// expected output: [1, 2, 0, 0]

// fill with 5 from position 1
console.log(array1.fill(5, 1));
// expected output: [1, 5, 5, 5]

console.log(array1.fill(6));
// expected output: [6, 6, 6, 6]


* `.concat()` glue arrays together to creat a new array
function remove(array, index) {
  return array.slice(0, index)
    .concat(array.slice(index + 1));
}
console.log(remove(["a", "b", "c", "d", "e"], 2));
// → ["a", "b", "d", "e"]

* `.trim()` remove whitespace (space, newlines, tabs and similar charatoer) from
  start to end of a string
console.log("  okay \n ".trim());
// → okay

* `padStart(lenght, 'padding charater')` it tkase the desired length and add apdding charatcter as
  arguments. 
console.log(String(6).padStart(3, "0"));
// → 006

* `split(":")` = split the array with : or space if empty (" ")  `join(". ")`
  join with .
let words = sentence.split(" ");
console.log(words);
// → ["Secretarybirds", "specialize", "in", "stomping"]
console.log(words.join(". "));
// → Secretarybirds. specialize. in. stomping
* `repeat(2)` = repeat 2 times
console.log("LA".repeat(3));
// → LALALA

* `.lenght` lenght of array, strings or others
let string = "abc";
console.log(string.length);
// → 3
console.log(string[1]);
// → b

* `.substr(3,12)` => 3 = from and inclusive; 12 = count from 3 onward 12 char
* string.substr(start, length)
var message = "We choose to go to the Moon!";
console.log(message.substr(3, 12)); // "choose to go"

* `toString()` = convert into string
* `toString(2)` = convert to binary, 
2 - The number will show as a binary value
8 - The number will show as an octal value
16 - The number will show as an hexadecimal value

var num = 15;
var a = num.toString(); // 15
var b = num.toString(2); // 1111
var c = num.toString(8); // 17
var d = num.toString(16); // f

`instanceof` operator return `true` or `false`

`arr.includes()` 
var array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

var pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true

console.log(pets.includes('at'));
// expected output: false

[1, 2, 3].includes(2);     // true
[1, 2, 3].includes(4);     // false
[1, 2, 3].includes(3, 3);  // false
[1, 2, 3].includes(3, -1); // true
[1, 2, NaN].includes(NaN); // true
* `.flat` => flatten and array.
var arr1 = [1, 2, [3, 4]];
arr1.flat(); 
// [1, 2, 3, 4]

var arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

var arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

* `parseInt(string, radix)`
* conver strings into integer
* radix = 

* check for interger `isInteger()`
function fits(x, y) {
  if (Number.isInteger(y / x)) {
    return 'Fits!';
  }
  return 'Does NOT fit!';
}

* `a.reverse` - only on arrays. so if you string you have to split, reverse than
  join.
var array1 = ['one', 'two', 'three'];
console.log('array1: ', array1);
// expected output: Array ['one', 'two', 'three']

var reversed = array1.reverse(); 
console.log('reversed: ', reversed);
// expected output: Array ['three', 'two', 'one']


* Recursive
if num is < 2 show 1, else show function
const factorial = number => {
  return number < 2 ? 1 : number * factorial(number - 1);
}

### REST parameters
* useful for a function to accept any numbers of arguments
function max(...numbers) {
  let result = -Infinity;
  for (let number of numbers) {
    if (number > result) result = number;
  }
  return result;
}
console.log(max(4, 1, 9, -2));
// → 9

let words = ["never", "fully"];
console.log(["will", ...words, "understand"]);
// → ["will", "never", "fully", "understand"]

### Math Object
* Eg `Math.max` `Math.min` `Math.sqrt` Math.cos(), sin, tan, acos, asin, atan
  (inverse), Math.PI. `Math.max(2,3,4,5)`
* Math.random() = randomw between zero (inclusive) and one (exclusive)
* Math.floor(x) = round  down to nearest whole number ; `Math.floor (2.9)` => 2
* Math.ceil = rounds up to a whole number `Math.ceil(2.04)` => 3
* Math.round() =to the nearest whole number
* Math.abs() takes the absolute value of a number. Change neg to positive.

## JSON (Javascript Object Notation)
* all property keys have to be surrouded by ""; and only simple data epxression
{
  "squirrel": false,
  "events": ["work", "touched tree", "pizza", "running"]
}
* `JSON.stringify(<object data>)` => convert object to data
* `JSON.parse(string)` => convert data into object

# Higher Order Function
* Example:
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
// → true
----------------------------------------------------------
function noisy(f) {
  return (...args) => {
    console.log("calling with", args);
    let result = f(...args);
    console.log("called with", args, ", returned", result);
    return result;
  };
}
noisy(Math.min)(3, 2, 1);
// → calling with [3, 2, 1]
// → called with [3, 2, 1] , returned 1
----------------------------------------------------------
function unless(test, then) {
  if (!test) then();
}

repeat(3, n => {
  unless(n % 2 == 1, () => {
    console.log(n, "is even");
  });
});
// → 0 is even
// → 2 is even

* Like `forEach(function)`, `filter(function)` and `map(function)` is standard
  array method

* `arr.filter(function())`
var words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]


* `reduce()` => build value by repeatedly taking a single element from the array
  and combining it with the current value.
  -paramataers to `reduce` => array, combining function, a start value
* function look like this 

function reduce(array, combine, start) {
let current = start;
for (let element of array) {
  current = combine(current, element);
}
return current;
}

console.log(reduce([1, 2, 3, 4], (a, b) => a + b, 0));
// → 10

* Find duplicate numbers in array

let a = [ 1,2,4,6,1,3];
let b = [];
let len = a.length // for time efficiency
a.sort(); // sort the array;
let _temp;

for (let i = 0; i < len; i++) {
  if (a[i] === _temp) {
    b.push(a[i]);
    a[i] = _temp
  }
}
console.log(b) // [1,1]
* `some()` => takes a test function and teslls you wether that function return
  tru for any of the elements in the array.
var array = [1, 2, 3, 4, 5];

var even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true

* emoji 🐴🧜‍♀️ => access cmd + ctrl + spacebar. below method, all use index in
  teh bracket as arguments
  - charCodeAt() - method give you a code unit.
  - codePointAt() -  give a full Unicode Charater
  - `for / loop` can used on strings for emoji

### Destructing
ref: https://codeburst.io/es6-destructuring-the-complete-guide-7f842d08b98f
* breaking down a complete structure into simpler part
* we had to use a pair of enclosing parentheses (()) in the assignment
  expression. 

// Initialize local variables
let country = 'Canada';
let firstname = 'John';
let lastname = 'Doe';

const student = {
    firstname: 'Glad',
    lastname: 'Chinda',
    country: 'Nigeria'
};

// Reassign firstname and lastname using destructuring
// Enclose in a pair of parentheses, since this is an assignment expression
({ firstname, lastname } = student);

// country remains unchanged (Canada)
console.log(firstname, lastname, country); // Glad Chinda Canada


# Object-oriented programming
* set of techniques that use objects(and related concepts) as central principle
  of program organization
* core of Object-oriented programming - divide programs into smaller pieces and
  make each piece responsible for managing its own state

## Encapsulation
* core of Object-oriented programming - divide programs into smaller pieces and
  make each piece responsible for managing its own state
* Pieces interact with each other through `interface`, using modeled as objects.
* Thier interface consists of specific set of methods and properties. 
* public - Properties part of the interface
* private - outside code should not be touching.
* public and private properties. private properties commonly indicate with
  underscor (_) character at the star of the property names.
* Separating interface from implementation is a great idea. This is call
  Encapsulation

## Methods
* properties taht hold function values.
let rabbit = {};
rabbit.speak = function(line) {
  console.log(`The rabbit says '${line}'`);
};

rabbit.speak("I'm alive.");
// → The rabbit says 'I'm alive.'

* when function is called as a method - looked up as a property and immediately
  called, as in object.method() - the binding called `this` in its body
  automatically points at the object that it was called on.
* think of `this` as extra parameter which passed in different way
function speak(line) {
  console.log(`The ${this.type} rabbit says '${line}'`);
}
let whiteRabbit = {type: "white", speak};
let hungryRabbit = {type: "hungry", speak};

whiteRabbit.speak("Oh my ears and whiskers, " +
                  "how late it's getting!");
// → The white rabbit says 'Oh my ears and whiskers, how
//   late it's getting!'
hungryRabbit.speak("I could use a carrot right now.");
// → The hungry rabbit says 'I could use a carrot right now.'
* function `call` method to pass it explicitly, which take `this` value (type: "hungry") as its
  first argument and treats further arugements as normal parameters.
speak.call(hungryRabbit, "Burp!");
// → The hungry rabbit says 'Burp!'

* Array function - do not bind `this` but can see the this binding of the scope
  around them. 
function normalize() {
  console.log(this.coords.map(n => n / this.length));
}
normalize.call({coords: [0, 2, 3], length: 5});
// → [0, 0.4, 0.6]

## Prototypes
* Objects have properties and prototype
* `Object.prototype` is the great ancestral prototype, the entity behind almost
  all objects
* `Function.prototype` & `Array.prototype`
console.log(Object.getPrototypeOf(Math.max) ==
            Function.prototype);
// → true
console.log(Object.getPrototypeOf([]) ==
            Array.prototype);
// → true
* `Object.create` to create an object with a sepcific prototype; creating
  object instances without first creating constructors (when you only create few
  instance of an objects)
let protoRabbit = {
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
};
let killerRabbit = Object.create(protoRabbit);
killerRabbit.type = "killer";
killerRabbit.speak("SKREEEE!");
// → The killer rabbit says 'SKREEEE!'

## Classes
* class defineds the shape of a type of object
* `constructor function` to create many similar objects. constructor create and
  display looks like this:
planet1 = new Planet("Jupiter", 8, "Gas Giant");
planet1.show();

var buildPlanet = function (name, position, type) {
    var planet = {};

    planet.name = name;
    planet.position = position;
    planet.type = type;

    planet.showPlanet = function () {
        var info = planet.name;
        info += ": planet " + planet.position;
        info += " - " + planet.type;
        console.log(info);
    };
    return planet;
};

* change to use `this`
var Planet = function (name, position, type) {
  this.name = name;
  this.position = position;
  this.type = type;
  this.showPlanet = function () {
  var info = this.name + ": planet " + this.position;
  info += " - " + this.type;
  console.log(info);

var planets = [
    buildPlanet( "Jupiter", 5, "Gas Giant" ),
    buildPlanet( "Neptune", 8, "Ice Giant" ),
    buildPlanet( "Venus", 2, "Terrestrial" )
];

* `constructor` - `new` in front of a function call, the function is treated as
  a constrcutor. => an object with the right prototype is automatically created,
  bond to `this` in the function, and returned at the end of the function.

function Rabbit(type) {
this.type = type;
}
Rabbit.prototype.speak = function(line) {
  console.log(`The ${this.type} rabbit says '${line}'`);
};

let weirdRabbit = new Rabbit("weird");

* A constructor function name usually starts with a capital letter — this convention is used to make constructor functions easier to recognize in code.
function Person(name) {
  this.name = name;
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name + '.');
  };
}
* how do we call a constructor to create some objects?
1. add the following lines
* `new` keyword is used to tell the browser we want to create a new object
  instance, parrenthesese for the result to sotred in a variable
var person1 = new Person('Bob');
var person2 = new Person('Sarah');
2. save your coe and reload it in the browser, and try entering the following
   lines into your JS console:
person1.name
person1.greeting()
person2.name
person2.greeting()

* Creating our finished constructor
function Person(first, last, age, gender, interests) {
  this.name = {
    'first': first,
    'last' : last
  };
  this.age = age;
  this.gender = gender;
  this.interests = interests;
  this.bio = function() {
    alert(this.name.first + ' ' + this.name.last + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
  };
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name.first + '.');
  };
}

person1 = new Person('Bob', 'Smith', 32, 'male', ['music', 'skiing']);



## Class notation
* `class` start a class declaration => allow to define a constructor and a set
  of methods all in a single place
* `constructor(type)` - provides the actual constructor function, will be bound
  to name `Rabbit`
class Rabbit {
  constructor(type) {
    this.type = type;
  }
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
}

let killerRabbit = new Rabbit("killer");
let blackRabbit = new Rabbit("black");
* Object() constructor
let person1 = new Object();
*


## Overriding derived properties

## Maps
* a map (noun) is a data structure that associates values(the keys) with other balues.
let ages = {
  Boris: 39,
  Liang: 22,
  Júlia: 62
};

console.log(`Júlia is ${ages["Júlia"]}`);
// → Júlia is 62
console.log("Is Jack's age known?", "Jack" in ages);
// → Is Jack's age known? false
console.log("Is toString's age known?", "toString" in ages);
// → Is toString's age known? true
* class called `Map`, it sotres a mapping and allows any types of keys
* methods `set, get` and `has` are part of the interface of `Map` object
let ages = new Map();
ages.set("Boris", 39);
ages.set("Liang", 22);
ages.set("Júlia", 62);

console.log(`Júlia is ${ages.get("Júlia")}`);
// → Júlia is 62
console.log("Is Jack's age known?", ages.has("Jack"));
// → Is Jack's age known? false
console.log(ages.has("toString"));
// → false

## Polymorphism
* the fancy word for the ability of multiple object types to implement the same functionality is polymorphism. Just in case you were wondering.

## Iterator Interface
* `Symbol.iterator`
* `.next()`,`done:`, `value:` 



# SHORT HAND

* compare item which is not in an specific array
if (!sequence[A[i]]) {
        counter++;
    }

* put element in the same as the index position
array[A[i]] = A[i]
