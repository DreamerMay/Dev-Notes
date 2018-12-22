
## Setting up React
`https://cdnjs.cloudflare.com/ajax/libs/react/15.6.1/react.min.js`
`https://cdnjs.cloudflare.com/ajax/libs/react/15.6.1/react-dom.min.js`

In codePen required this in html
```
<script crossorigin src="https://unpkg.com/react@16/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>

<div id="app"></div>
```

# Structure and Method
* Function name need to be Capital
* style use as `className`
* Create a function that have to render to the DOM using JSX
* Need Babel to act as Preprocessor so we can access html code in React/JS
* ReactDOM => render JS function as a component and render in browser. It renders with 2 argument (what, where) => (app, document.querySelector('#app') )
* Configurate component dynamically with `props` 
* Output data with { } in html format

Eg:
```
function Person(props) {
  return (
    <div className="person">
      <h1>{props.name}</h1>
      <p>Your Age: {props.age}</p>
    </div>
  );
}

var app = (
   <div>
      <Person name="Max" age="18" />
      <Person name="Manu" age="38" />
   </div>
)

ReactDOM.render(app, document.querySelector('#app'));
```

## ES6
* 

### Arrow Function
all are same with return 4
```
const multiple = number => number * 2;
const multiple = (number) => number * 2;
const multiple = (number) = {
  return (number * 2);
}

```
### Import and export (Modules)


