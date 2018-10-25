






















































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
<input velue={this.state.term}> control element
