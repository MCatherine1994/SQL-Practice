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
