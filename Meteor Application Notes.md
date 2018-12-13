## Meteor Application  
**To Create:**  
```
meteor create app_name  
```
**To Run:**  
```
cd app_name
meteor 
```
**To Check the Running Environment:**
```
import { Meteor } from 'meteor/meteor';
if(Meteor.isDevelopment) //check if in development mode
if(Meteor.isProduction) //check if in production mode
```
**To Clear Space:**  
```
$ meteor reset  // reset the database
$ meteor npm prune  // remove unused packages
```
**Meteor Method:**
```
Meteor.methods({
  funcName() {
    if (something) {
      return false;
    }
    return true;
  },
});

Meteor.call('funcName', (error, result) => {
  if (error) {
    console.log(error.reason);
  } else if (!result) {
    console.log(result);
  }
});
```
**Routes:**
```
// startup/client/routes.jsx
export const renderRoutes = () => {
  return (
    <Router history={browserHistory}>
      <Switch>
        <Route path="/" exact render={HomePage} />
        <Route path="/sub" component={SubPage} />
        <Route render={NotFoundPage} />
      </Switch>
    </Router>
  );
};

export default 'renderRoutes';
```
**Meteor Startup Render:**
```
// in main.jsx
Meteor.startup(() => {
  render(<Header />, document.getElementById('header')); // these id are in main.html
  render(renderRoutes(), document.getElementById('render-target'));
  render(<Footer />, document.getElementById('footer'));
});
```
