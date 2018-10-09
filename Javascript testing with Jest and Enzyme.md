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
#### **Simulate button onClick event:**   
```
wrapper.find('#button').simulate('click');
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
const spy = jest.spyOn(wrapper.instance(), 'func');
wrapper.update();
wrapper.instance().func(anyprops);
expect(spy).toHaveBeenCalled();
expect(spy).toHaveBeenCalledTimes(3);
```
#### **Test Property:**  
```
expect(defaultwrapper.instance().props.name).toEqual('Peter');
```
#### **Javascript function to reformat a dictionary:**  
```
// expect result could be like the sample data at the end of this component
const reformat = (data) => {
  const newformatData = {};
  Object.keys(data).forEach((key) => { // key here will be Cases and Percapita
    Object.keys(data[key]).forEach((element) => {
      if (!d3.keys(newformatData).includes(element)) { // check if the current type is initialed
        newformatData[element] = {};
      }
      const currenttype = data[key][element];
      // will be like data['201802']['Cases'] = [{pv: AB, DA:1, TA: 2}, {pv: BC, DA:1, TA: 2}, {pv: MB, DA:1, TA: 2}]
      for (let i = 0; i < currenttype.length; i += 1) {
        const currentprov = currenttype[i].province;
        const forcurrentym = { 'benefit month': key };
        Object.keys(currenttype[i]).forEach((category) => {
          forcurrentym[category] = currenttype[i][category];
        });
        if (d3.keys(newformatData[element]).includes(currentprov)) { // check if the current province is initialed
          newformatData[element][currentprov].push(forcurrentym);
        } else {
          newformatData[element][currentprov] = []; // initial
          newformatData[element][currentprov].push(forcurrentym);
        }
      }
    });
  });
  return newformatData;
};
```
