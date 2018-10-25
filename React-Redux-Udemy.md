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
