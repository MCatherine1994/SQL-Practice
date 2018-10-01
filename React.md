## **React.js**  
#### **[Tutorial](https://reactjs.org/docs/hello-world.html)**  
#### **Component Construct:**  
```
import PropTypes from 'prop-types';
import React, { Component } from 'react';
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
* @summary Update the state value
* @param {number} value
* @returns {none} null
*/
  handleChange = (value) => {
    this.setState({ anyState: value });
  }

  /**
 * Renders a Loading Dots component
 * @returns {JSX} returns React element
 */
  render() {
    const { any } = this.props;
    return (
      <div>
      {any_element i.e. this.state.anyState}
      </div>
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
Number.parseFloat(datum[m.metric]).toFixed(2)
```
