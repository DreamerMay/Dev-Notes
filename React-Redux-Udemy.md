#Redux Simple Starter Course

clone file

install NPM package =>

1. npm install  => install all package in reactsimplestarter
2. npm start

bundle.js => Webpage and Bebel take all files in src file bundle into one js file

component/view  => code that produce HTML; collection of javascript function that produce  HTML

.jsx => javascript code which ultimately can produce HTML

React divert into 2 separate library
Core React library: work with react components and nest them together
ReactDOM library : Take the component and insert it to the DOM  

render in DOM needs to be instances. Changing 'App' => '<App />'
- second element to show the location of the DOM/html file which get the class/id to render. Eg. document.querySelector('.container')

Create each component in each file under .js within 'Components file'


##Install Youtube API
Get youtube API_KEY from Console Google Developer

### Install npm youtube api
npm install --save youtube-api-search

--save => save into our package.json file

Add `import React from 'react';` to all component file

Need to export each component out to index.js
`export default SearchBar`

We need to link our own component file, we need to provide path
`import SearchBar from './components/search_bar';`

To upgrade a functional component to class based component (more intellectual components)
* Functional Component :
`const SearchBar = () => {
  return <input />;
}`

* React Based Component Class
=> Explain : Define new class SearchBar and extend all
 functionality in React.Component has  
 => Render Method : with every class created, we need to have a render method  
`class SearchBar extends React.Component {

}`

# Functional Components
* taking in some information and spitting out some JSX
import React, { Components } from 'react';
=> import React but pull all "Components" from react

class SearchBar extends Components{
   => extend Components to SearchBar to get all the functions

onInputChange() => usually how you name the event handler
handle/on + Name of the input/element + name of the event
=> whenever the input changes, action the even handler

<input onChange={this.onInputChange} />
onChange => when changes occur
{this.onInputChange} => event handler


event.target.value => log out only the value instead of the whole event


Non ES6
```
class SearchBar extends Component {
  render() {
    return <input onChange={this.onInputChange} />
  }

  onInputChange(event) {
      console.log(event.target.value);
  };
};
```

ES6 Version
```
class SearchBar extends Component {
  render() {
    return <input onChange={event => console.log(even.target.value)} />;
  }
}
```

## State
* Is a plain JS object use to record and react to user events
* Each class state that we define have it own state object
* If stage have been changed, class will be re-render again

### Initialise state
```
constructor(props) { => this function is called automatically when a new class is create
  super(props); => call the parent part of Component as super

  this.state = { term: ''}; => Initialising variable/ state; Creating a new object to assign to this state. Object we pass include property (term:'', this means update the property of the input.
}

```

`this.setState({ term: event.target.value }) `
this.setState => this is to inform react the state is changing; we only update our state by calling this

{ term: event.target.value } => this is the changed state


`Value of the input : { this.state.term }` : located in render return. return the updated input.

### Control Field
<input value={this.state.term}> control element


## ES6
videos: videos === video

<VideoList videos={this.state.videos} />
VideoList getting data from parent part SearchBar by passing with this.state.videos as props

{video} ==== const video = props.video;

### Interpolation ES6

url = 'https://www.youtube.com/embeded/' + videoId;

TO

url = `https://www.youtube.com/embeded/${videoId}`

Throttle
npm install --save lodash

## Three Tenets of Components
* Component Nesting
* Component Reusability
* Component Configuration

use {} when use javascript variables.

## Component Hierarchy
App -> is the parent component
CommentDetail -> is the child/children component

### Props
* system for passing data from a parent component to a child component
* Goal is to customize or configure a child/nested component


