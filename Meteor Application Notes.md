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
**Mongo Collection:**
```
// in api collectionName.js
import { Mongo } from 'meteor/mongo';
export const collectionName = new Mongo.Collection('collectionName');

// on server side main.js
import '../imports/api/collectionName';

// in mongo python
import MySQLdb 
from MySQLdb.cursors import DictCursor
def collectionName(connection):
    """collectionName application"""
    log = logging.getLogger(LOG_NAME)
    log.debug('collectionName')

    database = MySQLdb.connect(
        read_default_file="file_directory",
        use_unicode=True,
        cursorclass=DictCursor,
    )
    cursor = database.cursor()
    documents = {}

    # select all avaliable data
    cursor.execute("""
        any_query
    """)

    # mirror the default aggregation into mongo
    documents = cursor.fetchall()
    documents = sorted(alls, key=lambda rec: (rec['attr1'], rec['att2']))
  
    mirror(connection, dict(name='collectionName', documents=[document]))
    log.info('%d observations for collectionName', len(documents))

    database.close()
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
  const user = {
    User: headers.get('user'),
    Email: headers.get('email'),
  };

  render(<Header
    user={user}
    isDevelopment={Meteor.isDevelopment}
    navbar={[<MenuContainer />]}
  />, document.getElementById('header'));
  render(<ConnectError />, document.getElementById('connecterror'));  // these id are in main.html
  render(renderRoutes(), document.getElementById('render-target'));
  render(<Footer />, document.getElementById('footer'));
});
```
