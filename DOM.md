# DOM
```
document.getElementById('id') => id='id'
document.getElementsByTagName('li') =>  <li>
documnet.getElementsByClassName(className);
document.querySelector('ul li.catname');
document.querySelectorAll('ul li.catname');
```

### For example, to replicate this CSS: 
```
body {
  background-color: pink;
  padding-top: 10px;
  font-style: oblique;
}
```
### We would need to do this: '-' must change to camelCase
```
let pageNode = document.querySelector('body');
pageNode.style.backgroundColor = 'pink';
pageNode.style.paddingTop = '10px';
padgeNode.style.fontStyle = 'oblique';
```

### Changing element in HTML
// You can set innerHTML yourself to change the contents of the node:
pageNode.innerHTML = "<h1>Oh Noes!</h1> <p>I just changed the whole page!</p>"

// You can also just add to the innerHTML instead of replace:
pageNode.innerHTML += "...just adding this bit at the end of the page.";

## Creating elements
```
document.createElement(tagName);
document.createTextNode(text);
document.appendChild();
```

## Events

domNode.addEventListener(eventType, eventListener, useCapture);

### Some Events Type
* mouse events: mousedown, mouseup, click, dbclikc, mousemove, mouseover,
  mousewheel mouseout, contetmenu
* touch events: touchstart, touchmove, touchend, touchcancel
* keyboard events: keydown, keypress, keyup
* from event: focus, blur, change, submit
* window events: scroll, reisze, hashchange, load, unload

## Window Object
window.location.href; // Will return the URL
window.navigator.userAgent; // Tell you about the browser
window.scrollTo(10, 50);
window.alert("Hello world!"); // Same things
alert("Hello World!");

window.console.log("Hi"); // Same things
console.log("Hi");

## Animation
To call a function once after a delay:
window.setTimeout(callbackFunction, delayMilliseconds);
To call a function repeatedly, with specified interval between each call:
window.setInterval(callbackFunction, delayMilliseconds);
window.clearTimeout(timer);
window.clearInterval(timer);