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
// on server slide, run into database
const mysqlQuery = function mysqlQuery(queryDate, callback) {
  pool.getConnection((err, connection) => {
    if (err) {
      const connectError = new Meteor.Error(
        'mysqlQuery.methods.unable.to.connect',
        'Error getting a connection to the database...',
      );
      callback(connectError, null);
    } else {
      const CMD = `SELECT * FROM table where any_attr = ${queryDate} `;
      // execute will internally call prepare and query
      connection.execute(
        CMD,
        (error, results, fields) => {
          // And done with the connection.
          connection.release();

          // Handle error after the release.
          if (error) {
            const connectError = new Meteor.Error(
              'mysqlQuery.methods.query.error',
              'Error querying the database...',
            );
            callback(connectError, null);
          }
          // Don't use the connection here, it has been returned to the pool.
          // console.log('Caseload Query results: ', results.length);
          callback(null, results.map((d) => {
            return {
              a: d.a,
              b: d.b,
            };
          }));
        },
      );
    }
  });
};

Meteor.methods({
  getQueryResult: (filters) => {
    const response = Meteor.wrapAsync(mysqlQuery)(filters);
    return response;
  },
});

// in component, call meteor method
Meteor.call('getQueryResult', querydata, (error, result) => {
  if (!error) {
    const result = result;
  } else {
    console.log(error);
  }
});
```
