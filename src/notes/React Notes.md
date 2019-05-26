# React Notes
## React CDN Links for use in HTML pages 
``` html
<script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script> 
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script> 
```


When using React.createElement, there are three things that you have to pass to `React.createElement;`, the HTML tag that the element will be, the attributes that you want to give to the element and what will be inside of the element 

If there is no attributes that need to be passed in, type in `null` 

An example of  `React.createElement` is below: 

``` jsx
const name = "Sean" 

const nameElement = React.createElement( 
  "h1", 
  null, 
  name 
) 
```

 When using Babel with React, Babel will take the JSX version code and compiles the code into what React understands. For example the below code: 

``` jsx
function NameComponent(props) { 
  return <h1>{props.name}</h1> 
} 
```

And will compile to the code below so React knows what to do with the code 
``` jsx
Function NameComponent(name) { 
  return React.createElement( 
    "h1", 
    null, 
    name 
  ) 
} 
```
   - When info is "passed in" through the render method, this is done through the use of props 
   - When the data that is needed for a component is in another object, those items are accessed through `props.<object name>.<item>` 

## Multiple children and parent component 

When working with React there will almost always be the case where there will be multiple children components of a parent component.  

Each child component will have a variable where they will store their data.

For instance one could have a return method using the variable `{props.img}`.  

When accessing this child element in the parent element, the way that the data is accessed is telling the child element what data to pass it.  

So for the above example the data would be accessed by the code `img={props.user.img}`.  

The variable name will be the same as the last part of the child element. Below is an example of the sample code: 

``` jsx
    function Avatar(props) { 
      return <img src={props.img} /> 
    } 

    function Label(props) { 
      return <h1>Name: {props.name}</h1> 
    } 

    function ScreenName(props) { 
      return <h3>Username: {props.username}</h3> 
    } 

    function Badge(props) { 
      // const user = props.user;
      // const img = user.img; 
      // const name = user.name; 
      // const username = user.username; 
      return ( 
        <div> 
          <Avatar img={props.user.img}/> 
          <Label name={props.user.name}/> 
          <ScreenName username={props.user.username} /> 
        </div> 
      ) 
    } 

    ReactDOM.render( 
      <Badge user={{ 
        name: 'Tyler McGinnis', 
        img: 'https://avatars0.githubusercontent.com/u/2933430?v=3&s=460', 
        username: 'tylermcginnis' 
      }} />, 
      document.getElementById('app') 
    ) 
```

Inside of the Badge function, it would be possible to create a new variable as a `const` with the name of `user`. The variable `user` can be set to `props.user` so that you would not have to type all three words every time. All that would have to be typed is `user.img` and so on. This could be taken a step farther as is shown in the commented out variables that are listed in the code above. 

   - React can be "ran" on the client or from the server 
   - In the head tag of an HTML document there are 3 script tags that need to be added. 
``` html
  <script src="<Location of react.js file>"></script> 
  <script src="<Location of react-dom.js file>"></script> 
  <script src="<Link to Babel>"></script> 
```
   - JSX is essentially writing HTML inside of JavaScript code 

A basic example of how to display Hello World to the browser 
``` jsx
    <div id="area"></div> 
    <script type="text/babel"> 
      Var HelloWorld = React.createClass({ 
        Render: function() { 
          Return (<h1>Hello World</h1>) 
        } 
      }); 
        ReactDOM.render( 
          <HelloWorld />, 
          document.getElementById("area") 
        ); 
    </script> 
```

   - Props is the same thing as properties 
   - When using props in React they are placed inside of React.createClass 

Here is an example of the Hello World that has a prop type of name 


``` jsx
    <div id="area"></div> 
    <script type="text/babel"> 
      Var HelloWorld = React.createClass({ 

        propTypes: { 
          Name: React.PropTypes.string.isRequired 
        }, 
        getDefaultProps: function(){ 
          Return { 
            Name: "Scott" 
          } 
        }, 
        Render: function() { 
          Return (<h1>Hello {this.props.name}</h1>) 
        } 
      }); 
        ReactDOM.render( 
          <HelloWorld name="Tim" />, 
          document.getElementById("area") 
        ); 
    </script> 
```


   - In a component, getDefaultProps is what will be returned if there is nothing passed into ReactDOM.render 
   - When setting propTypes for a compenent the available prop types are: array, bool, func, object, number and string 
   - The .isRequired on the end of the prop types means that this is required 
   - Data goes down through components from parent to child and not the other way around 
   - A variable can be passed into JSX by wrapping the variable in curly braces {} 
   - State is on a per component basis and that state is within the component itself 
   - While it is not required, when making a custom method, use an underline before the name of the method. (i.e. _addByOne) 



 ## To setup React using NPM 

   1. Create the folder where the application will be 
   2. Create an index.html file 
   3. In that file create a stock html file 
   4. Inside that html file create a div with an id of app or whatever you would like to call it 
   5. Inside the same HTML file make a script tag with the source set to the app.js file or whatever you would like to call it 
   6. In the terminal, navigate to the folder where the app is located 
   7. Run the command `npm init`  
   8. Answer all of the questions that are asked or using all of the defaults is fine 
   9. Open the `package.json` file 
   10. Add a comma after `"license": "ISC"` 
   11. On the next line type  
``` js
    "devDependencies": { 
      "babel-core": "^6.7.*", 
      "babel-loader": "^6.2.*", 
      "babel-preset-es2015": "^6.6.*", 
      "babel-preset-react": "^6.5.*", 
      "webpack": "^1.12.*", 
      "webpack-dev-server": "^1.14.*" 
    }, 
      "dependencies": { 
      "react": "^15.0.0", 
      "react-dom": "^15.0.0" 
    } 
```
   1. In the terminal run the command `npm install` which will install all of the modules 
   2. Next we need to make the `webpack.config.js` file, which should look something like this: 
``` js
    module.exports = {
      entry: "./src/App.js", 
      output: { 
        path: __dirname, 
        filename: "app.js" 
      }, 
      module: { 
        loaders: [{ 
          test: /\.jsx?$/, 
          exclude: /node_modules/, 
          loader: "babel", 
          query: { 
            presets: ["es2015","react"] 
          } 
        }] 
      } 
    }; 
```
  14. In the terminal run the command `<node_modules/.bin/webpack-dev-server>` to start the dev server 



## Create React App with create-react-app CLI 

   1. Install `create-react-app` if not installed globally `npm install -g create-react-app` 
   2. In the terminal go to where you want to create the folder for the react app 
   3. Type `npx create-react-app <name of react app>` 
   4. Change directory to the new react app folder 
   5. Type `npm start` 

   - For the render function of a component there can be only one div at the highest level 
   - While using create-react-app, `npm start` will run the app in development mode.  
   - When a react app is in development mode, the app can be viewed at `http://localhost:3000` 
       - If using create-react-app the webpage for the app will open when "npm start" is ran 
        - To add a component to App.js enter the following command inside of the return function of render. `<<Component Name> />` 
        - To display the items of an array, the `.map` function needs to be use on that array. For example: 
``` jsx
    { 
      list.map(item => { 
        return item; 
      }) 
    } 
```
   - When mapping out an array, each child element has to have a unique key. This can be done by typing `key={<some unique key>}` 

   - All of the event handler functions can be run within JSX, such as `onClick()`, `onMouseEnter`, or `onKeyDown()` 

   - If the error "this is undefined" or "cannot read property of 'setState' of undefined" is called, this needs to be bound using the constructor method, like this: 
``` jsx
    constructor(props) { 
      super(props); 
      this.<the method that created the error> = this.<the method that created the error>.bind(this); 
    } 
```
   - The state of a component can be set within the constructor method, using the following code: 
   ``` jsx
    this.state = { 
      title: "App Title" 
    }; 
   ```
   And displayed with this code 
``` jsx
    <div className="App"> 
      <h1>{this.state.title}</h1> 
    </div> 
```
   Below is an example of a method that changes the state of the component using onClick 
``` jsx
    onClick() { 
      this.setState({ 
        title: "New app title" 
      }); 
    } 
```



## Adding another component to an application 

  1. Create a new file for the component with the file name format as `<new component name>.js` 
  2. Either copy the file data from an existing component or add the following code that is the base component file structure: 
``` jsx
    import React, { Component } from 'react'; 

    class <New Component Name> extends Component { 
      render() { 
        return ( 
          <div className="<class name for new component>"> 
          </div> 
        ); 
      } 
    } 
     
    export default <New Component Name>; 
```

   3. Add the line  `import <New Component Name> from "<location of new component file>";` to the parent component of the new component 
   4. Add the line `<<New Component Name> />` to the return function of the render method of the parent component 

Within React there is the ability to pass and use props between the parent and child components. In the parent component you can set what certain props are set to such as: 
``` jsx
<MyComponent  
title="This is the component title" 
name = "Sean" 
/> 
```

In the child component, how those props will look can be chosen like this: 
``` jsx
<h1>Title: {this.props.title}</h1> 
<h2>Name: {this.props.name}</h2> 
```
So that there is no need to type this.props for every prop, this can be done using the code `const {title, name} = this.props;` 

After that the props in the child component can be written like this: 
``` jsx
<h1>Title: {title}</h1> 
<h2>Name: {name}</h2> 
```

PropTypes are used to set which props can be used and to set the specific data types that those props can be 

PropTypes are no longer included in the base React package and have to be installed using NPM, using the command `npm i -S prop-types` 

To use PropTypes in a component, it needs to imported using the line `import PropTypes from 'prop-types';` 

To set the propTypes for each of the props the following format of code will be used: 
``` jsx
const propTypes = { 
  name: PropTypes.string.isRequired, 
  title: PropTypes.string.isRequired 
} ; 
```
 - Not all propTypes have to have .isRequired, only the props that are indeed required 

The last line of code that is needed to use propTypes within a component is the line  

`<Component Name>.propTypes = propTypes;` that should be placed before the export line 

If a prop uses a different prop type from what is specified or a required prop is not used, there will be a "Failed prop type" warning will show on the browsers dev console 

The "Failed prop type" warning will say why the warning message appeared  

Within a component, the default values of each prop can be set using the following code: 
``` jsx
const defaultProps = { 
  name: "Default Name" 
} 
```
And then this line of code `<Component Name>.defaultProps = defaultProps;` needs to be placed before the export line of the component  

## React Lifecycle 

There are 4 phases in the lifecycle of a React component: Initialization, Mounting, Updating, and Unmounting 

- There is no need to bind lifecycle methods, because React will do that for you 

### Mounting Phase 

`componentWillMount` - executed before the component is about to mount on the DOM. THIS HAS/WILL BE DEPRICATED SOON!!!!

`Render` - mounts components to the DOM 

`componentDidMount` - This code is executed after the component successfully mounted to the DOM. This is when third  party JS libraries that need to access the component should be initialized. This is also where API calls or fetching of any data that is needed should be made. 

- For the mounting lifecycle phase, the order that things happen is 
  1. All of the code that is in the `constructor` will be ran
  2. The component(s) will `render`
  3. The code (if it exists) inside of `componentDidMount` will run

### Updating Phase 

`shouldComponentUpdate` - Accepts the arguments nextProps and nextState. If a false is returned, the component will not update. If true is returned, then the component will update  

`componentWillUpdate` - Accepts the arguments nextProps and nextState 

`componentDidUpdate` - Accepts the arguments `prevProps` and `prevState`. This will run whenever there is an update to the component. If the update is done through an input box, the component will update after each letter is entered or after a button is clicked. 

`componentWillUnmount` - Could be used to remove a "listener" from a component, that would usually be added inside of `componentDidMount`


*** Finish this section***** 



## Inputs 

An input can have a default value set and that is done with `defaultValue=<default value>` 

An input with a default value is an uncontrolled input 

An input that uses the value key is a controlled input and because of this there is no way to change what is in the input 

Use controlled inputs when there is a need for a fine grain control over the data that is entered into an input 

To change what is input there needs to be an `onChange` event handler for that input 

An example of an `onClick` event handler that is ran when clicking a button looks like `<button onClick={this.<function name>}>`

To make an event handler for an `onChange` event handler 

   1. Add an `onChange` method onto the input that is a controlled input. An example is `onChange={this.updateName}` 

   2. In the constructor method bind the function that is used for the event handler. An example is `this.<function name> = this.<function name>.bind(this);` 

   3. Create the function that will be taking care of the event handler. An example is: 
```jsx
    updateName(event) { 
      this.setState({ <prop name>: event.target.value}); 
    } 
```



## React Router 

   In order to use React Routers, the package needs to be installed using the command `npm install --save react-router-dom` 

   On any component that uses React Router, the import line that needs to be used is `import { BrowserRouter as Router, Route, Link } from "react-router-dom";` 

   The main component that is using React Router is wrapped in a `<Router>` tag 

   The links to the other "pages" use the following code format `<Link to="/">Home</Link>`

   Each link then finds which component to load bu use of the Route tags, like this example: 
``` jsx
    <Route exact path="/" component={Home} /> 
    <Route path="/about" component={About} /> 
    <Route path="/topics" component={Topics} /> 
```
   - It looks like only the root path needs to use exact path 

   Each React Router component uses the same format. An example is: 
``` jsx
    const Home = () => ( 
      <div> 
        <h2>Home</h2> 
      </div> 
    ); 
```
Props are used to share data between components and state only exists within the component where state is set  



## React State Usage 

When creating a React application, the 2 things that you have to think about is the state of the components and how the UI looks based off of that state. The UI is a function of the states of the components 

A functional component should only be used if the component takes in data and then renders something along with that data. Another way to think about functional components is that they are nothing more than render methods. 

State should be stored as high as possible on the Parent/Child tree and then passed down through props 

To be able to manage the state of a component, the component needs to be a class component instead of a function component 

A class component looks like the code below: 
``` jsx
class App extends React.Component { 
  render() { 
    const friends = ["Jordan", "Mike", "Jake"] 
    return ( 
      <div> 
        <FriendsList list={friends} />  
      </div> 
    ) 
  } 
} 
```

Once the component is class component, the way that state is able to set and changed is through the method.

Inside of the constructor method, the first thing that has to be included is the super function and pass it props 

Then the state is set within the constructor method through the `this.state ={<state>}` 
An example of a constructor method is below: 
``` jsx
constructor(props) { 
  super(props) 

  this.state = { 
    friends: ["Jordan", "Mike", "Jake"] 
  } 
} 
```
To access the state from the return function of the render method, use the following code `<FriendsList list={this.state.friends} />`  

If there is a method that exists in the parent component and it needs to be passed down to a child component,  there needs to be a reference to the method when calling the child component. An example of this is in the code below: 
``` jsx
<FriendsList  
  list={this.state.friends}  
  onRemoveFriend={this.handleRemoveFriend} 
/>  
```
`handleRemoveFriend` is the method that is needed in the `FriendsList` component that is in the parent component 

When there is a function that needs to be executed on a given event, like a button click, there has to be an arrow function that invokes the desired method. An example of this is`<button onClick={()=> props.onRemoveFriend(name)}>Remove</button>` 

The function would have to use an arrow function, because if there is no arrow function, the function would run once the component is loaded. 

When there is a component that is using this.setState, the function that is setting state has to use the .bind method and this is done within the constructor method. Here is a sample of this `this.handleRemoveFriend = this.handleRemoveFriend.bind(this)` 

If there is an error that says `this.setState is not a function`, then there is a function that has not been bound and the above code needs to be implemented.

In order to add a simple text box and button with React all of the code that is needed is:

``` jsx
<input 
	type="text"
    placeholder="new friend"
 />
 <button>Submit</button>
```

While there are 2 ways to set the state of a component and those are 

``` jsx
//Example 1
this.setState(()=>({
	input: value
}))

//Example 2
this.setState({
    input: value
})
```

Example 1 is the way that would be correct if there is a need to know what the previous state was. Whereas Example 2 will work when there is no need to know what the previous state was. With Example 1, React is passing in the current state or `currentState` to the `setState`

When adding elements to an array we don't want to modify the array directly and because of this, the `.push()` shouldn't be used. How this should be done is through the use of `.concat()` which will add the new element to the array and create a new array 

When there is an array that is an array of objects instead of an array of string. Just referencing something like `name` will not work. In an instance like this the object dot notation would need to be used like `friend.name`

In order to have specific components render or not render, this can be done will the lifecycle method `shouldComponentUpdate`. This method should return either true or false based on if that component should render. This may have a performance or render performance hit with it. Make sure to check the overall performance before doing this.

A re-render will happen anytime `setState` is changed or anytime that a component receives new props 

When fetching from a data source, the fetch should be done within `componentDidMount` and if there is a need to update the component with other data this should be done within `componentDidUpdate` 

AJAX calls should not be done in the constructor!!