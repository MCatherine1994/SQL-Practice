## **React**  
#### **[Tutorial](https://reactjs.org/docs/hello-world.html)**  
#### **[React Select](https://github.com/JedWatson/react-select)**  
#### **Tab to switch between two items:**  
```
// Create tabs
<div className="uk-width-auto@m uk-margin-remove">
  <ul className="uk-flex-right" uk-tab="animation: uk-animation-slide-left-medium, uk-animation-slide-right-medium" >
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
