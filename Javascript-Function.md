let a = parseInt("1010", 2)
to binary. 2 control the type, 8 is oct, 16 is..

let fix = result.toFixed(2);
fix to 2 decimal

let string = fix.toString();


### NodeList 
`document.querySelectorAll('.controls input'`
* only few methods compared to normal array
*

- dataset 
* is object to `data-<name>` anything with `data-`
`<div class="controls">
    <label for="spacing">Spacing:</label>
    <input id="spacing" type="range" name="spacing" min="10" max="200" value="10" data-sizing="px" data-color="test">


<div class="controls">
    <label for="spacing">Spacing:</label>
    <input id="spacing" type="range" name="spacing" min="10" max="200" value="10" data-sizing="px" data-color="test">
`


To show in table: console.table();

### Selector
const category = document.querySelector('.mw-category') => '.' => className

const links = Array.from(category.querySelectorAll('a')) => select tag
const links = [...category.querySelectorAll('a')] => ... create Array

const de = links
               .map(link => link.textContent)
               .filter(streetName => streetName.includes('de'));

               