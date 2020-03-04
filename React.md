## **React.js**  
#### **[Tutorial](https://reactjs.org/docs/hello-world.html)**  
#### **[Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)**
#### **[React Lifecycle Methods](https://www.tutorialspoint.com/reactjs/reactjs_component_life_cycle.htm)**  
#### **Component Construct:**  
```
import PropTypes from 'prop-types';
import React, { Component } from 'react';
import AnyOtherComponment, { AnyOtherMethod } from '../components/AnyOtherComponment'; // AnyOtherMethod is the method in the AnyOtherComponment

/**
* A CompName component
*/
class CompName extends Component {
  /**
  * Initialize the React element
  * @param {props} props React element properties
  */
  constructor(props) {
    super(props);
    this.state = { anyState: true };
    this.handleChange = this.handleChange.bind(this);
  }
  
    /**
* @summary Support actions for when the Alphabet Component is first mounted
* @returns {none} returns nothing
*/
  componentDidMount() {
   // this.handleChange should be other function that handles the event, 
   // in this case, call the handleChange function every second
    setInterval(this.handleChange, 1000);
  }

  /**
* @summary Update the state value
* @param {string} name
* @param {number} value
* @returns {none} null
*/
  handleChange = (name, value) => {
    this.setState({ [name]: value });
  }

  /**
 * Renders a Loading Dots component
 * @returns {JSX} returns React element
 */
  render() {
    const { any } = this.props;
    return (
      <div> // <React.Fragment>
        {any_element i.e. this.state.anyState}
        <div className="uk-grid uk-child-width-expand@s" uk-grid={null}>
          {any_thing want to display in grid}
        </div>
      </div>  // </React.Fragment>
    );
  }
}
export default CompName;
// Specifies the default values for props:
CompName.defaultProps = {
};

CompName.propTypes = {
};

```
#### **Tab to switch between two items:**  
```
// Create tabs
<div className="uk-width-auto@m">
  <ul className="uk-flex-right" uk-tab="animation: uk-animation-slide-left" >
    <li><a href="#" onClick={() => { this.setState({ tabstate: 'one' }); }}>one</a></li>
    <li><a href="#" onClick={() => { this.setState({ tabstate: 'two' }); }}>two</a></li>
  </ul>
</div>

// Use tabs
let show = '';
if (this.state.tabstate === 'one') {
  show = 'one'; // if component, show = (<MyComponent />);
} else if (this.state.tabstate === 'two') {
  show = 'two';
}

// Return in Render
return (
  {show}
);
```
#### **[React Select](https://github.com/JedWatson/react-select):**  
```
<fieldset className="uk-fieldset">
  <Select
    name="any_name"  
    placeholder={defaultShow}   // the default content to display
    closeMenuOnSelect  // default is true, close the drop list after click a selection
    onChange={this.handleOnChange} // handle when the selection changed
    options={selectOption} // the drop list for selection
    styles={colourStyles}
    value={displayValue} // the value want to display
  />
</fieldset>
```
#### **PropTypes:**  
```
export default componentName;

// Specifies the default values for props
componentName.defaultProps = {
  prop_one: false,
  prop_two: [], 
  prop_three: (() => { return null; }),
  prop_four: {},
  prop_five: 123,
};

componentName.propTypes = {
  prop_one: PropTypes.oneOfType([   // accept two types
    PropTypes.shape({
      sub_prop: PropTypes.string,
    }),
    PropTypes.bool,
  ]),
  prop_two: PropTypes.arrayOf(PropTypes.object),
  prop_three: PropTypes.func,
  prop_four: PropTypes.shape(),
  prop_five: PropTypes.number,
};
```
#### **SetState Callback:**  
```
// will call the callback instantly after set the state to be true, this is the way to set state synchronous
this.setState({ currentState: true }, () => {
  setTimeout(() => {
    if (currentState) {
      this.setState({ otherState: true });
    }
   }, 1500);
});
```
#### **React.Fragment:**  
```
if <div> </div> has no meaning except for the linting problem, then use <React.Fragment></React.Fragment> instead
<React.Fragment>
  <any_component />
</React.Fragment>
```
### **JavaScript:**
#### **Array:**  
##### **ForEach:**  
```
Object.keys(dictionary).forEach((element) => {
  // do something
});
```
##### **Add or Delete:**  
```
// push
array.push(new_element);
// pop 
array.pop(old_element);
// delete a certain element

//insert at the beginning
```
##### **Includes:**  
```
my_array.includes(key)
```
##### **Get rid of white space in string:**  
```
str = str.replace(/\s/g, '');
```
##### **Convert to other type Array:**  
```
// string array convert to integer array
 const NumberArray = StringArray.map(Number)
```
#### **CheckType:**  
```
// check if is string
if (anyArray instanceof String) {
}
```

#### **Map:**
##### **ArrayMap:**  
```
anyarray.map((key) => {
  return (
    <li key={key}>
       {any_display}
    </li>
  );
})
```
##### **Create Map:**  
```
const inputArray = [{ title: 'Math', grade: '95' }, { title: 'Science',  grade: '85' }, { title: 'Engineer', grade: '90' }];
const mapInput = new Map(inputArray.map((i) => { return [i.title, i]; }));
// if want to get 'Math' from mapInput
mapInput.get('Math');
mapInput.get('Math').grade;
```
#### **Number:**  
```
// round
Math.round(number);
// leave two decimals
Number.parseFloat(datum[m.metric]).toFixed(2);
// convert to string
Number.toString();
```
#### **Object(Dictionary):**  
```
// get the keys
Object.keys(dictionary);
// get the element values
Object.values(dictionary);

// revert keys and values of a dictionary
Object.fromEntries(Object.entries(obj).map(([k, v]) => ([v, k])))

// get unique values from the object
Array.from(new Set(Object.values(dictionary)))

// dynamic add each element of an arry or object
Object.keys(dictionary).map((key) => {
  return (
  <div key={Math.random() * 100}>
    {key}
    {dictionary[key]}
  </div>
  );
})
```
#### **Date Time:**  
```
console.log(new Date('July 20, 69 00:20:18').getMilliseconds());
```
#### **Simulate Click Event:**  
```
/**
* @summary reset the state to trigger the tour
* @param {selector} selector d3 selector
* @returns {none} unknow
*/
simulateClick = (selector) => {
  const e = document.createEvent('UIEvents');
  e.initUIEvent('click', true, true /* ... */);
  d3.select(selector).node().dispatchEvent(e);
}
```
#### **HTML DOM getElementsBy... Method:**  
```
document.getElementsByClassName('example');
document.getElementById('example');
document.getElementsByTagName('example');
document.querySelector('[any_attr_name="attr_value"]');
```
