## Styling Method

html style <div style="background-color: red;"></div>
JSX style <div style={{ backgroundColor: 'red' }}></div>

html style <div style="border: 1px></div>

<button style={{ backgroundColor: 'blue', color: 'white'}} ></button>

`class` => JSX => `className` (avoid to create class function)

## JS variable in JSZ
* create const variable within the component `const getButton = "Click Me!"` and
  call it out within the componenet with `{getButton}`
* create const variable within the component `const getButton = { text: 'Click Me!'}` and
  call it out within the componenet with `{getButton.text}`
* create function outside the component `const getButton = () => {"Click Me!"}` and
  call it out within the componenet with `{getButton()}`