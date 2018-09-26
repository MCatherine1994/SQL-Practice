## **React.js**  
#### **[Tutorial](https://reactjs.org/docs/hello-world.html)**  
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
##### **Includes:**  
```
my_array.includes(key)
```
#### **Map:**
```
anyarray.map((key) => {
  return (
    <li key={key}>
       {any_display}
    </li>
  );
})
```
