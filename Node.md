## **Node.js**  
#### **[Build an npm package](https://docs.npmjs.com/creating-and-publishing-private-packages)**:  
```
// On local drive
$ mkdir my_project
$ cd myz-project
$ git init  // create a git repository
// Add components, install packages, tests, README
```
Npm package can't be written in ES6,  so need to convert the files.  
```
$ babel src --out-dir dist --copy-files -s inline // covert all .jsx files in src to dist in correct format, copy rest css files  
```
