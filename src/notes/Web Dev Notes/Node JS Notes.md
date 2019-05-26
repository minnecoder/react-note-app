**<u>Steps to create Node app</u>**

1. Create a folder for the application
2. Navigate to the folder
3. Type `npm init` and answer questions about the application
4. Open the newly created package.json file and enter the dependencies that are needed for the application 
5. Type `npm install` to install all of the dependencies for the application 
   1. Another alternative to entering all of the dependencies is to run `npm install <package name> --save` which will install the dependency adds the dependencies to the `package.json` file	 

Install the nodemon package globally - `npm install -g nodemon` 

Type `nodemon` to start it 

​    - with nodemon there is no need to restart node when changes are made  

 

The lines that are needed in the node.js file (index.js is default) are below 

```javascript
const express = require("express"); 
const port = 3000;  \
const app = express(); 
app.get("/",(req,res)=>{ 

}); 

```



A schema is the information that will be used for each item in that schema. 

Example: 

```javascript
const userSchema = new Schema({ 
	username: String, 
	googleid: String 
}); 
```



A model is how the data will be in the database 

**<u>To create a JavaScript file that would store keys so that they are not visible on github</u>**

1. Create a file that is named `keys.js` or another preferred name

2. Enter code that looks something like the code below:

   ``` javascript
   module.exports = {
       google:{
           clientID: <Google Client ID>,
           clientSecret: <Google clientSecret>
       },
       mongodb:{
          dbURI:<MongoDB URI> 
       }
   }
   ```

3. In the file where the information is needed, include the line `const keys = require("./keys");` with all of the information that is needed to be changed for specific use

4. To use the key values from the `keys` file the example data would be accessed by using the following syntax `keys.google.clientID` 