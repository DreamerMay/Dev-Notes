# React

## Setup
* Install React
`npm install -g create-react-app`

* Create React file
```
create React your_app_name_here
create-react-app xxx
```

* Create and move files
mkdir components
mv App.js components
touch components/Xxx.js

index.js file
import App from './components/App';

* install
```
npm install jsonp-es6
curl https://code.jquery.com/jquery-1.12.4.js > js/jquery.js
```

## ReactJS Components
* Components
  - function that return HTML to render a piece of the page
  - written eight JS or JSX
  - return only single element (but element can have multiple child)
  - can either received data from its parent component of from component itself
  Should pass (FIRT - Focused, Independent, Reusable, Small, Testable)


### State
Stateful component need 3 things
  - A `constructor` method
      * called auto when component is created => initialize method
  - A `super` method
      * sit inside `constructor` method
      * give component all the function
  - A `this.state` property
      * default is undefined
      * can set `this.state` to be a value

### Lifecycle
Stateful React components have 3 main parts to it lifecycle :
* *Mounting* - Component inserted into DOM
  - `getInitialSate()` :
  - `componentWillMount()` :
  - `componentDidMount()` :
* *Updating* - Component re-rendered into virtual DOM to determine if required updating in DOM
* *Unmounting* - Component being removed from DOM


---------------------------------------------------------------
### Checkbox

Create component
```
        <MaterialCheckboxStyled>
          <Checkbox
            checked={this.state.materialCostIncluded}
            className="MyCheckbox"
            id="MyOption1"
            kind="square-primary"
            label="Materials included in cost estimate"
            name="myOption"
            onChange={handleMaterialChange}
          />
        </MaterialCheckboxStyled>
```

Add initial state in Class = `materialCostIncluded: false`
```
class CostEstimate extends PureComponent {
  state = {
    hoursFocused: false,
    priceFocused: false,
    materialCostIncluded: false
  };
```

add handleMaterialChange event 
```
 handleMaterialChange = (e) => {
    console.log("click");
    this.setState({
      materialCostIncluded: !this.state.materialCostIncluded
    })
  }
  ```
  
Add const in render()
` const { handleMaterialChange } = this;`



## React-Spring 
animation for React
