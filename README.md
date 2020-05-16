*********************
# ReactDocumentation
*******************
# States and Props
## States Definition:-
 * State is a special object that holds dynamic data, which means that state can change over time and anytime based on user actions or certain events.
 * State is private and belongs only to its component where defined, cannot be accessed from outside, but can be passed to child components via props.
 * State is initialized inside its component’s constructor method.
 * When a change in the state is made, state shouldn’t be modified directly. Instead, state updates should be made with a special method called setState( ).
 * State should not be overly-used in order to prevent performance problems.
   1. **props.someProp** corresponds with an attribute of the tag but **state.someState** doesn’t
   2. You can create default values for state.someState in the constructor of class(Component)
   3. In component(class), you cannot change the value of props.someProp, but can change the values of state.someState.
   
## Creating The State:-
 * If you’re familiar with object-oriented programming, you know that there is a structure called class.
 * A class has a special method called constructor( ) and it is being called during object creation. We can also initialize our object properties or bind events inside the constructor( ).
 * The same rule applies to state. Since state is also an object, it should be initialized inside the constructor method:
### Small app in states:-
 * Start New project, open cmd your folder location and type cmd (npx create-react-app props)
 * Open project folder in the editor.
 * open src folder, and search app.js file, and open the App.js file default code remove, and add this code.
 
 
   #### Below example shows how to use state: 

```
import React, { Component } from 'react';
class App extends React.Component {
 constructor() {
      super();
      this.state = { name: "Raja" };
      }
      render() {
              return (
                  <div>
                      <h1> Welcome to  { this.state.name }</h1>
                  </div>
              );
     }
}
export default App;
```

### Output:-
  * how to run the server 
  * enter into your project folder and open command prompt type cmd (npm start)
  * output from above code
  
![Img](img\state.PNG)
 
## Props Definition:-
  * “Props” is a special keyword in React, which stands for properties and is being used for **passing data from one component to another**. But the important part here is that data with props are being passed in a **uni-directional flow**. (one way from parent to child) 
  * Further more, **props data is read-only**, which means that data coming from the parent should not be changed by child components. 
  * It is an object which stores the value of attributes of a tag and work similar to the HTML attributes. 
  * It is similar to function arguments. 
  * Props are **immutable** so we **cannot modify the props from inside the component**. Inside the components, we can add attributes called props. These attributes are available in the component as this.props and can be used to render dynamic data in our render method. 
  * **this.props.property name** => Passing parameters from one component to another component
 ## Using Props in React
   1. You can create default values for props.someProp
   2. You can set values for props.someProp from the attribute someProp tag
   3. From the inside of Component(class), you don’t have anyways to assign new values to the props.someProp
    * I will be explaining how to use Props step by step.
     1. Firstly, define an attribute and its value(data)
     2. Then pass it to child component(s) by using Props
     3. Finally, render the Props Data

  ### Below example how to passing data with Props:
```
import React, { Component } from 'react'
class App extends Component{
  render(){
    return(
      <div>
      <h3> Parent Child</h3>
      <ChildComponent name="First Child"/>
      </div>
    );
 }
}
const ChildComponent = (props) => {
  return <p> ChildComponent {props.name} </p>;
};
export default App;

```
## output
  * output from above code
 ![props](img\props.PNG)
## state vs props:-

![state vs props](img\statepropsd.PNG)

### example:
![hai](img\exp.PNG)


# JSON Rendering

 * JSON stands for ***JavaScript Object Notation***.
 * JSON is a lightweight format for storing and transporting data.
 * JSON is often used when data is sent from a server to a web page.
 * JSON is "self-describing" and easy to understand.
 ![json img](img\jsonimg.PNG)
 
 ## JSON Syntax Rules :-
  * Data is in name/value pairs
  * Data is separated by commas
  * Curly braces hold objects
  * Square brackets hold arrays
  ### example JSON Formate:-
   * JSON arrays are written inside square brackets.
   ```
   {
  "name":[
    {
      "name1": {
        "key" : "value",
        "key1" : "value"
      }
    },
    {
      "name1": {
        "key" : "sdc",
        "key1" : "ap"
      }
        }
    ]
}
```
## small app using JOSN rendering
 * start the new project 
 * open project folder
 * create a data folder in src folder
 * next create a data.json file in data folder and copy code or type the bellow code
 ```
 {
  "profiles":[
    {
      "basicInformation": {
        "firstname" : "React",
        "lastname" : "JS"
      }
    },
    {
      "basicInformation": {
        "firstname" : "sdc",
        "lastname" : "ap"
      }
        }
    ]
}
```
* after that open **App.js** file and type the bellow code
```

import React from 'react';
import Data from './data/data.json';

function App(){
  return(
    <section>
           <header className="header">
           <Home/>
           </header> <br/> <br/>
      </section>
  )
}
let Home=()=>{
    var info=Data.profiles;
    return(
        <section className="raja">
            {info.map((i,index)=>(
                <div className="card main">
                  <div className="card-body">
                      <h2 className="card-title"> {i.basicInformation.firstname} </h2>
                      <h5 className="card-text"> <em> {i.basicInformation.lastname}</em></h5>
                   </div>
                </div>
            ))}
        </section>
    )
}
export default App;
```
* add your own css or bootstrap
### output bellow
  * Output from above code
![json](img\json.PNG)


# Router
 * A React Router is a collection of navigational components. These are React components themselves and these React components enable us to navigate among various views or navigate among various pages. Now, the React Router itself provides larger components than route matching components and a navigation components. 
 * Routing is a process in which a user is directed to different pages based on their action or request. ReactJS Router is mainly used for developing Single Page Web Applications. React Router is used to define multiple routes in the application. When a user types a specific URL into the browser, and if this URL path matches any 'route' inside the router file, the user will be redirected to that particular route.
 ## Need of React Router
  *React Router plays an important role to ***display multiple views in a single page application***. Without React Router, it is not possible to display multiple views in React applications. Most of the social media websites like Facebook, Instagram uses React Router for rendering multiple views.
 ## React Router Installation
  * React contains three different packages for routing. These are:
   #. ***react-router***: It provides the core routing components and functions for the React Router applications.
   #. ***react-router-native***: It is used for mobile applications.
   #. **react-router-dom**: It is used for web applications design.
  
   * It is not possible to install react-router directly in your application. To use react routing, first, you need to install react-router-dom modules in your application. The below command is used to install react router dom.
   * Install and configure your application to use React Router
   * Configure the routes for React router to enable you to navigate to various pages within your React application
 ## Installing and Configuring React Router
  * First install React Router into your project by typing the following at the prompt
  * open cmdv in your project type bellow cmd.
  ```
  npm install react-router-dom
  ```
 ## Components in React Router 
  * **`<BrowserRouter>**`: It is used for handling the dynamic URL.
  * **`<HashRouter>**`: It is used for handling the static request.
  
  ### Small app the router
   * **Step-1**: In our project, we will create two more components along with App.js, which is already present.
   * Create a new files named About.js and Contact.js in the components folder and add the following to it:
   * add bellow code About.js
   ```
   import React from 'react'
   class About extends React.Component {
     render() {
       return <h1>About</h1>
     }
   }
   export default About 
  ```
  * Add bellow code Contect.js
   ```
   import React from 'react'
   class Contact extends React.Component {
     render() {
       return <h1>Contact</h1>
     }
   }
   export default Contact;
   ```

  * **Step-2**: For Routing, open the App.js file and import all the three component files in it. Here, you need to import line:
  ```import { Route, Link, BrowserRouter as Router } from 'react-router-dom'```
  * which helps us to implement the Routing. Now, our App.js file looks like below.
  
  ```
  import React from 'react'
import { Route, Link, BrowserRouter as Router } from 'react-router-dom'
import About from './About'
import Contact from './Contact'
class App extends React.Component {
  render() {
    return (
      <div>
        <Router>
         <div>
           <h1>This is the React Router</h1>
           <Route path="/home" component={Home} />
           <Route path="/about" component={About} />
           <Route path="/contact" component={Contact} />
         </div>
       </Router>
      </div>
    )
  }
}
let Home=()=>{
    return(
      <section>
        <h3> Home Page </h3>
      </section>
    )
}
export default App;
```
  * Step-3: Open command prompt, go to your project location, and then type npm start. You will get the following screen.
  
  ### Output:-
  start page
  ![1](img\1.PNG)
  Home page
  ![1](img\2.PNG) 
  About Page
  ![1](img\3.PNG)
  Contact page
  ![1](img\4.PNG)
  
  
  * **Step-4**: In the above screen, you can see that Home component is still rendered. It is because the home path is '/' and about path is '/about', so you can observe that slash is common in both paths which render both components. To stop this behavior, you need to use the exact prop. It can be seen in the below example.
* add this code in App.js file
```<Route exact path="/" component={Home} />```

## Adding Navigation using Link component
 * Sometimes, we want to need multiple links on a single page. When we click on any of that particular Link, it should load that page which is associated with that path without reloading the web page. To do this, we need to import <Link> component in the App.js file.
 #### What is < Link> component?
  * This component is used to create links which allow to navigate on different URLs and render its content without reloading the webpage.
 
## Example

* Add this is code in App.js

```
import React from 'react'
import { Route, Link, BrowserRouter as Router } from 'react-router-dom'
import About from './About'
import Contact from './Contact'
class App extends React.Component {
  render() {
    return (
      <div>
        <Router>
         <div>
           <h1>This is the React Router</h1>
           <ul>
            <li><Link to="/">Home</Link></li>
            <li><Link to="/about">About</Link></li>
            <li><Link to="/contact">Contact</Link></li>  
          </ul>
           <Route exact path="/" component={Home} />
           <Route path="/about" component={About} />
           <Route path="/contact" component={Contact} />
         </div>
       </Router>
      </div>
    )
  }
}
let Home=()=>{
    return(
      <section>
        <h3> Home Page </h3>
      </section>
    )
}
export default App;
```
## output
![h](img\h.PNG)
* After adding Link, you can see that the routes are rendered on the screen. Now, if you click on the About, you will see URL is changing and About component is rendered.
![h](img\a.PNG)

## Task1:
Creat app Navigation Bar bellow image
![nav](img\nav.PNG)
