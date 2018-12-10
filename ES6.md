Webpack
Babel
Babel.loader

TODO: installation method for webpack and babel 


npm init


# Features

* Let and Const
* `${}`
## Template Literal
    `
    include all indentation within the backticks 
    `${} => provide multiple line strings. If put together it's same line
    ${}`
    `
## Spread Operator :  ... 
    adding arrays variable into an array with ...
    Eg: 
    ```
    	var cats = ["Tabby", "Siamese", "Persian"];
		var dogs = ["Golden Retriever", "Pug", "Schnauzer"];

		var animals = ["Whale", "Giraffe", ...cats, "Snake", ...dogs, "Coyote"];

		console.log(animals);
    ```
## Map
    - Holds key value pairs
    - Any type can be used as a key
```
		var course = new Map();
		course.set('react', {description: 'ui'});
		course.set('jest', {description: 'testing'});

		console.log(course);
		console.log(course.react); => undefined
		console.log(course.get('react')); => {description: "ui"}

		var details = new Map([
			[new Date(), 'today'],
			['items', [1, 2]]
		]);

		console.log(details.size); => 2

		details.forEach(function(item) {
			console.log(item);              => today
		});                                 => (2) [1, 2]
```

## Destructuring Objects

```
const personalInformation = {
    firstName: 'Dylan',
    lastName: 'Israel',
    city: 'Austin',
    state: 'Texas',
    zipCode: 73301
};
const {firstName: fn, lastName: ln} = personalInformation;
console.log(`${fn} ${ln}`);
```

Output : Dylan Israel

## Destructring Arrays
```
let [firstName, middleName, lastName] = ['Dylan', 'Coding God', 'Israel'];
lastName = 'Clements';
console.log(lastName)
```

output : Clements

## Object Literal

```
function addressMaker(city, state) {
    const newAdress = {city: city, state: state};
    console.log(newAdress);
}
addressMaker('Austin', 'Texas');
```
Output : {city: "Austin", state: "Texas"}

## For of Loop
```
let incomes = [62000, 67000, 75000];
let total = 0;

for (const income of incomes) {
    console.log(income);
    total += income;
}
```

Output income: 62000, 67000, 75000
Output total : 207000

```
let fullName = "Dylan Coding"

for (const char of fullName) {
    console.log(char)
}
```

Output: 
D
y
l
a
n
.
.
.

## Spread Operator (unwrap)

let example1 = [1,2,3,4,5,6];
let example2 = [...example1];
let example3 = [example1]

console.log(example2);
output: [1,2,3,4,5,6]

example2.push(true);
console.log(example2);
output: [1,2,3,4,5,6,true]

console.log(example3);
output: [[1,2,3,4,5,6]]

## Rest Operator

```
function add(nums) {
    console.log(arguments)
}

add(4,5,6,7,12)
```
output: {0: 4, 1: 5, 2: 7, 3: 8, 4: 12}

```
function add(...nums) {
    console.log(nums)
}

add(4,5,6,7,12)
```
output: [4, 5, 7, 8, 12]