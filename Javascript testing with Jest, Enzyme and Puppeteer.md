## **Javascript testing with Jest and Enzyme**
#### **Unit test pattern for React componment:**   
```
describe('Component Description', () => {
  const component = (
    <Component anyProperties={anyProperties} />
  );
  const wrapper = shallow(component);
  it('should be defined', () => {
    expect(Component).toBeDefined();
  });
  it('should match the snapshot', () => {
    expect(wrapper).toMatchSnapshot();
  });
});
```
#### **Integration test pattern:**  
```
describe('Integration Test for WebTour Component', () => {
  const component = <Component />;
  const page = shallow(component);

  beforeEach(() => {  
    document.body.innerHTML = '<div id="testing"><div id="test-component"></div>' +
      '<div class="test-title">Hello, this is the integration test</div>' +
      '</div>';
    ReactDOM.render(component, document.getElementById('test-component'));
    window.Element.prototype.getComputedTextLength = function test() {
      return 200;
    };
  });
  
  it('Should be defined', () => {
    expect(component).toBeDefined();
  });

  it('Should contains other components', () => {
    expect(page.find('Other_Component').length).toBeGreaterThan(0);
  });
  
  it('Expect function to be an instance of function', () => {
    expect(props.func).toBeInstanceOf(Function);
  });
  
  it('Function should been called when another component invoked",, () =>  {
    // suppose function change the page state flag, flag origin is false
    const spy = jest.spyOn(page.instance(), 'function');
    const otherComp = (<Other_Component function={spy} />);
    ReactDOM.render(otherComp, document.getElementById('test-component'));
    expect(page.state('flag')).toBe(false);
    simulateClick(document.getElementById('toggle-function'));
    expect(spy).toHaveBeenCalled();
    expect(page.state('flag')).toBe(true);
    simulateClick(document.getElementById('toggle-function'));
    expect(spy).toHaveBeenCalled();
    expect(page.state('flag')).toBe(false);
  });
});
```
#### **Functional testing example:**
```
import puppeteer from 'puppeteer';

describe('Component test', () => {
it('test should match screenshot', async () => {
jest.setTimeout(30000);
const browser = await puppeteer.launch();
const page = await browser.newPage();
await page.goto('http://localhost:3000/', { waitUntil: 'load' });
await page.waitForSelector('#any_id');
await page.screenshot({ path: 'screenshot.png' });
await browser.close();
});
});

```
#### **Simulate button onClick event:**   
```
wrapper.find('#button').simulate('click');
// enzyme find and click
wrapper.find('.classname').at(0).simulate('click');  // if there are multiple elements has the same classname, at(0) returns the first one
```
#### **Mocks:**   
##### **Mock Modules:**
```
Create a folder named "_mocks_" and store all the mock modules here.  
Depends on what is import in the component, in the mock file, need to export that.  
In the package.json, under the jest setting part, having:  
"moduleNameMapper": {
  "^module_name": "mock module path",
  "^meteor/meteor": "./tests/__mocks__/meteor/meteor.js", // example
}
Also need to clarify the unmock modules:
"unmockedModulePathPatterns": [
  "path to module",
  "./node_modules/react",
],
```
##### **Mock Functions:**  
```
// call the function
wrapper.instance().func(); 
// test function has been called
const spy = jest.spyOn(wrapper.instance(), 'func');  //'func' is the function name of the function in the component
wrapper.update();
wrapper.instance().func(anyprops);
expect(spy).toHaveBeenCalled();
expect(spy).toHaveBeenCalledTimes(3);
```
#### **Test Property and State:**  
```
expect(wrapper.instance().props.name).toEqual('Peter');
expect(wrapper.state('flag')).toEqual('true');
```
#### **Test d3 chart:**
```
import testChart from 'chart_directory';
describe('Reusable d3.js chart', () => {
  let chart = null;

  beforeEach(() => {
    chart = testChart();
  });

  it('Should be defined', () => {
    expect(testChart).toBeDefined();
  });

  it('Should be a function', () => {
    expect(testChart).toBeInstanceOf(Function);
  });
  
  // metehod to test api
  it('Should find and set width and height', () => {
    // Should exist not as 0
    expect(chart.width()).toBeGreaterThan(0);
    expect(chart.height()).toBeGreaterThan(0);
    // Should be able to be set
    expect(chart.width(500).width()).toEqual(500);
    expect(chart.height(450).height()).toEqual(450);
  });
 });
```
#### **[Difference of enzyme Shallow and Mount](https://blog.usejournal.com/testing-with-jest-and-enzyme-in-react-part-4-shallow-vs-mount-in-enzyme-d60cad73f85c)**  
