# Reactjs-interview-question-and-anwser


1- What is the virtual DOM?

DOM stands for 'Document Object Model'. It is a structured representation of HTML in the webpage or application. It represents the entire UI(User Interface) of the web application as the tree data structure.

The concept of Virtual DOM comes to make the performance of Real DOM better and faster. Virtual DOM is a virtual symbol of the DOM.
But the main difference is that every time, with each change, the virtual DOM gets updated instead of the actual DOM.
For example, the real and virtual DOM is represented as a tree structure. Every element in the tree is a node. A node is added to the tree when a new item is added to the application UI.
If the position of any elements changes, a new virtual DOM tree is created. The virtual DOM computes the minimum number of operations on the real DOM to make changes to the real DOM. It is efficient and performs better by reducing the cost and operation of re-rendering the whole real DOM.


2- Event handleing in React js.

React has the same events as HTML: click, change, mouseover etc.

example 1

function ActionLink() {  
    function handleClick(e) {  
        e.preventDefault();  
        console.log('You had clicked a Link.');  
    }  
    return (  
        <a href="#" onClick={handleClick}>  
              Click_Me  
        </a>  
    );  
}  

example 2

function ActionLink() {
  const handleClick = (e) => {
    e.preventDefault();
    console.log('The link was clicked.');
  }

  return (
    <button onClick={handleClick}>
      Click me
    </button>
  );
}


onmouseover : The mouse is moved over an element 
onmouseup : The mouse button is released 
onmouseout : The mouse  is moved off an element 
onmousemove: The mouse is moved 
Onmousedown: mouse button is pressed  
onload : A image is done loading 
onunload: Existing the page  
onblur : Losing Focus  on element  
onchange : Content of a field changes 
onclick: Clicking an object  
ondblclick: double clicking an object  
onfocus element getting a focus  
Onkeydown: pushing a keyboard key 
Onkeyup: keyboard key is released 
Onkeypress: keyboard key is pressed  
Onselect: text is selected 


3-what is props.

Props stand for "Properties." They are read-only components. It is an object which stores the value of attributes of a tag and work similar to the HTML attributes. It gives a way to pass data from one component to other components. It is similar to function arguments. Props are passed to the component in the same way as arguments passed in a function.

example

1- function Car(props) {
  return <h2>I am a { props.brand.model }!</h2>;
}

function Garage() {
  const carInfo = { name: "Ford", model: "Mustang" };
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand={ carInfo } />
    </>
  );
}

2- function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
    </>
  );
}

3- import React from 'react';
import ReactDOM from 'react-dom';
 
// sample component to illustrate props
class DemoComponent extends React.Component{
    render(){
        return(
 
                <div>
                    {/*accessing information from props */}
                    <h2>Hello {this.props.user}</h2>
                    <h3>Welcome to GeeksforGeeks</h3>
                </div>
            );
    }
}
 
ReactDOM.render(
    // passing props
    <DemoComponent user = "Harsh Agarwal" />,
    document.getElementById("root")
);

4-what is state.

The state is a built-in React object that is used to contain data or information about the component. A component’s state can change over time; whenever it changes, the component re-renders. The change in state can happen as a response to user action or system-generated events and these changes determine the behavior of the component and how it will render.


class Greetings extends React.Component {
  state = {
    name: "World"
  };
  updateName() {
    this.setState({ name: "Simplilearn" });
  }
  render() {

      return(
          <div>
              {this.state.name}
          </div>
      )
  }
}

Changing the state Object

class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  changeColor = () => {
    this.setState({color: "blue"});
  }
  render() {
    return (
      <div>
        <h1>My {this.state.brand}</h1>
        <p>
          It is a {this.state.color}
          {this.state.model}
          from {this.state.year}.
        </p>
        <button
          type="button"
          onClick={this.changeColor}
        >Change color</button>
      </div>
    );
  }
}


1- A state can be modified based on user action or network changes
2- Every time the state of an object changes, React re-renders the component to the browser
3- The state object is initialized in the constructor
4- The state object can store multiple properties
5- this.setState() is used to change the value of the state object
6- setState() function performs a shallow merge between the new and the previous state

5-what is class component and functional component.


Functional component 

import React, { useState } from "react";
 
const FunctionalComponent=()=>{
    const [count, setCount] = useState(0);
 
    const increase = () => {
        setCount(count+1);
    }
 
    return (
        <div style={{margin:'50px'}}>
            <h1>Welcome to Geeks for Geeks </h1>
            <h3>Counter App using Functional Component : </h3>
          <h2>{count}</h2>
            <button onClick={increase}>Add</button>
        </div>
    )
} 
 
 Class Component
import React, { Component } from "react";
 
class ClassComponent extends React.Component{
    constructor(){
        super();
        this.state={
            count :0
        };
        this.increase=this.increase.bind(this);
    }
     
   increase(){
       this.setState({count : this.state.count +1});
   }
 
    render(){
        return (
            <div style={{margin:'50px'}}>
               <h1>Welcome to Geeks for Geeks </h1>
               <h3>Counter App using Class Component : </h3>
               <h2> {this.state.count}</h2> 
               <button onClick={this.increase}> Add</button>
 
            </div>
        )
    }
}
 
export default ClassComponent;
 
export default FunctionalComponent;



6-different between class component and function component


7-What is React Hook's.

Hooks are the new feature introduced in the React 16.8 version. It allows you to use state and other React features without writing a class. Hooks are the functions which "hook into" React state and lifecycle features from function components. It does not work inside classes.

import React, { useState } from 'react';  
  
function CountApp() {  
  // Declare a new state variable, which we'll call "count"  
  const [count, setCount] = useState(0);  
  
  return (  
    <div>  
      <p>You clicked {count} times</p>  
      <button onClick={() => setCount(count + 1)}>  
        Click me  
      </button>  
    </div>  
  );  
}  
export default CountApp;


Basic Hooks

useState
useEffect
useContext

Additional Hooks

useReducer
useCallback
useMemo
useRef
useImperativeHandle
useLayoutEffect
useDebugValue

8-what is Axios

Axios allows us to communicate with APIs easily in our React apps. Though this can also be achieved by other methods like fetch or AJAX, Axios can provide a little more functionality that goes a long way with applications that use React.

using fetch method

const getPostsData = () => {
  fetch(‘https://jsonplaceholder.typicode.com/posts’)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.log(error));
  }
}
 getPostsData();
 
 using axios method
 
 const getPostsData = () => {
  axios
  .get("https://jsonplaceholder.typicode.com/posts")
  .then(data => console.log(data.data))
  .catch(error => console.log(error));
  };
 getPostsData();



import React from 'react';
import axios from 'axios';

export default class PersonList extends React.Component {
  state = {
    persons: []
  }

  componentDidMount() {
    axios.get(`https://jsonplaceholder.typicode.com/users`)
      .then(res => {
        const persons = res.data;
        this.setState({ persons });
      })
  }

  render() {
    return (
      <ul>
        {
          this.state.persons
            .map(person =>
              <li key={person.id}>{person.name}</li>
            )
        }
      </ul>
    )
  }
}

9-What is map function

The map() function is used to iterate over an array and manipulate or change data items. In React, the map() function is most commonly used for rendering a list of data to the DOM.

const Users = () => {
  const data = [
    { id: 1, name: "John Doe" },
    { id: 2, name: "Victor Wayne" },
    { id: 3, name: "Jane Doe" },
  ];

  return (
    <div className="users">
      {data.map((user) => (
        <div className="user">{user}</div>
      ))}
    </div>
  );
};


10- what is arrow function


11-what is reast and spred operator.

The JavaScript spread operator ( ... ) allows us to quickly copy all or part of an existing array or object into another array or object.

Assign the first and second items from numbers to variables and put the rest in an array:

const numbers = [1, 2, 3, 4, 5, 6];

const [one, two, ...rest] = numbers;


import React, { Component } from 'react';
  
// Details is a component in same folder
import Details from './Details'; 
class App extends React.Component {
  
  render() {
    var person = {
      name: 'User',
      age: 22
    };
  
    return (
      <div>
        {/* Details component which accepts props */}
        <Details {...person} title='Dear' />
      </div>
    );
  }
}
  
export default App;

12-what is closure

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment).

import { IRootState } from "@app/typings";
import * as React from "react";
import { useSelector } from "react-redux";

const PostUrlList: React.FunctionComponent = (props) => {
  const { posts, uid } = useSelector((state: IRootState) => state.account)

  const getPostUrl = (post: IPost) => {
    const availabilityPrefix = post.private ? "myprivateposturl" : "mypublicposturl"
    return `https://${availabilityPrefix}/post.id?uid=${uid}`
  };

  return (
    <div>
      {posts.map((post) => (
          <a key={post.id} href={getPostUrl(post)}></a>
      ))}
    </div>
  );
};

export default PostUrlList;


13-HOC

A higher-order component (HOC) is an advanced technique in React for reusing component logic. HOCs are not part of the React API, per se. They are a pattern that emerges from React's compositional nature. Concretely, a higher-order component is a function that takes a component and returns a new component



14-different between var,let and const.

15-lifecycle method of React.


16-what is context API.


17-what is redux


18-what is stateless and statefull component.

In React, a stateful component is a component that holds some state. Stateless components, by contrast, have no state. Note that both types of components can use props. In the example, there are two React components. The Store component is stateful and the Week component is stateless.


19-what is fragments.


20- what is controll and uncontroll component.

21-what is jsx.

22-





