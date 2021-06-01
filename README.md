# React-Cribsheet

> React is a **JavaScript library** for building User interfaces(UI). So after [CSS Cribsheet](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md) this is another initiative to make small notes on React which may help me or anyone else in the future. 


Before starting React we have to download and install **Node js** and **NPM**. If we use Linux, we can use the following commands :

``` shell

apt install nodejs
apt install npm

```

After that we can use the below command to install the package which will create react app:

``` shell

npm i -g create-react-app

```

I used `create-react-app@4.0.3`.We can use [Visual Studio Code](https://code.visualstudio.com/) as our code editor. Inside [Visual Studio Code](https://code.visualstudio.com/) we can install [Prettier - Code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) formatter to make our code prettier and easier to read/debug and [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets) for snippets of usable React codes.

___

## Context Table

|Topics|
|---|
|[Creating & Starting Application](https://github.com/sayeemabdullah/React-Cribsheet#creating--starting-application)|
|[How things work?](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#how-things-work)|
|[Hello World!](https://github.com/sayeemabdullah/React-Cribsheet#hello-world)|
|[ES6](https://github.com/sayeemabdullah/React-Cribsheet#es6)|
|[Adding Bootstrap](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#adding-bootstrap)|
|[Components](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#components)|
|[JSX](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#jsx)|
|[Props](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#props)|
|[State](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#state)|
|[Destructuring Arguments](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#destructuring-arguments)|
|[Rendering Lists](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#rendering-lists)|
|[Conditional Rendering](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#conditional-rendering)|
|[Handling Events & Binding Event Handlers](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#handling-events--binding-event-handlers)|
|[Lifecycle Hooks](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#lifecycle-hooks)|
<!---|[]()|
|[]()|
|[]()|
|[]()|
|[]()|
|[]()|
|[]()|
|[]()|
|[]()|
|[]()|--->
___


## Creating & Starting Application

To create our app we have to first go to our desired folder and use the below command:

``` shell

npx create-react-app name-of-our-project

```

And now to start our project we will use the following command after going to our project directory which is **react-app** for me:

``` shell

npm start

```

**npm** is for package and dependency management and **npx** is for project management.

After starting our project we will see **node_modules** which there are 3rd party libraries and react itself, **public** for public assets and **src** for basic components. 

To see the conversion of modern javascript to browser-compatible JavaScript we can use [Babel](https://babeljs.io/).

___

## How things work?

After creating the application we will find `index.html` under **public** folder so here where the magic happens. When you run your application it runs only this file. Inside this file we will find a single `div` like below: 

``` html

<div id="root"></div>

``` 

So it renders the div whose id is root. Now if we go to the `index.js` file under **src** we will find the following snippet of code:

``` js

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

```

So here it throws all the things inside **App** component to the div whose id is root. Now inside the `App.js` file which is also under **src** folder, we can add more components or write code there which will be rendered accordingly but we can also print or code without using `App.js` which is shown below in the [**Hello World**](https://github.com/sayeemabdullah/React-Cribsheet#hello-world) section. 

___

## Hello World!

To print **“Hello World!”** in our screen we can write the following code inside `index.js`:

``` js

import React from 'react';
import ReactDOM from 'react-dom';

const element = <h1>Hello World!</h1>
ReactDOM.render(element, document.getElementById('root'))

```

Here we import `react` for the components and `react-dom` for rendering the components in the DOM (Document Object Model).

___

## ES6

ES6 stands for ECMAScript 6 (6th version of ECMAScript) which was created to standardize JavaScript.

#### let

`let` is used to assign value to variables in a block that cannot be accessed outside.

#### var

`var` is used to assign value to variables that can be accessed anywhere.

#### const

`const` is used to assign value to variables that cannot be re-assigned anywhere in the code.

#### Objects & Object Destructuring

Objects are collections of key-value pairs. We can make an object like the below:

``` js

const person = {
    name: 'Sayeem',
    walk(){},
    run(){}
};

```

To access the members we can use `person.walk()` and `person[‘name’] = ‘Abdullah’`. 

We can extract the properties like the below code without going the traditional way:

``` js

const address = {
    street: '',
    city: '',
    country: ''
};

const {street , city , country } = address;
```

#### this

`this` is a keyword in JavaScript which doesn’t behave the same as C# or Java. The value of `this` is determined by how a function is called. If it is called a method in an object it will return the reference to that object and if it's called outside of an object it will return the global object or window object.

If we want to fix that we can use the bind function so that we get reference every time like below: 

``` js
const walk = person.walk.bind(person);
``` 

#### Arrow Functions

We have used a function like below before:

``` js

const cube = function(number){
    return number * number * number;
}

```
We can write the above code in arrow function like below:

``` js

const cube = (number) => number * number * number;

```

The arrow function is easier to read and easier to write. 

####  Array.map Method 

``` js
const colors = ['red' , 'green', 'blue'];
const items = colors.map(color => `<li>${color}</li>`);
```

The above code is pretty self-explanatory. 

#### Spread Operator

To combine two arrays we normally use code like below:

``` js

const first = [1,2,3];
const second = [4,5,6];

const combined = first.concat(second);

``` 
But if we can use a spread operator we can do that more easily and add anything before, between or after arrays like the following:

```js

const first = [1,2,3];
const second = [4,5,6];

const combined1 = [...first, ...second];
const combined2 = ["a", ...first, "b" ,...second, "c"];


```

#### Classes

To declare a class, we can use the class keyword and create object like below: 

``` js
class Person{
    constructor(name){
        this.name = name;
    }

    walk(){
        console.log("walk");
    }
}

const person = new Person('Sayeem');
console.log(person.name);

```

#### Inheritance

We can inherit the above class into another class by the following code:

``` js

class Teacher extends Person{
    
    constructor(name,degree){
        super(name);
        this.degree = degree;
    }
    
    teach(){
        console.log("teach");
    }
}

```

Here `super()` is used to set a name in the parent class. 


#### Modules 

We can divide our project files into different modules which will help us to organize our code better. To do so we can create two files `person.js` and `teacher.js`. Then do the following :

``` js

//person.js

export class Person{
    constructor(name){
        this.name = name;
    }

    walk(){
        console.log("walk");
    }
}

```
``` js

//teacher.js

import {Person} from './person';

export class Teacher extends Person{
    
    constructor(name,degree){
        super(name);
        this.degree = degree;
    }
    teach(){
        console.log("teach");
    }
}

```

``` js

//index.js

import {Teacher} from './teacher';

const teacher = new Teacher("Sayeem" , "BSc");
console.log(teacher.degree);

```
Modules are private in default and to make them private we use **export** before **class**.

___

## Adding Bootstrap

First, we need to install bootstrap using the terminal like below:

``` shell

$ npm i bootstrap

``` 

To import it in our index.js we will use the following code :

``` js

import 'bootstrap/dist/css/bootstrap.css';

``` 

___

## Components

The heart of React application is a component. A component is a piece of UI. A tree of components makes a complete UI. In the root of the tree is the main component (App). There are two types of component types. 

* **Stateless Functional Component**
* **Stateful Class Component**

A **Stateless Functional Component** is just another javascript function which is shown below:

``` js

import React from "react";

function Greet() {
  return <h1>Hello World!</h1>;
}

export default Greet;

```

So here we have exported our function and which can be later called in any other component. We have called **Greet** in `App.js` as shown below:

``` js

import "./App.css";
import Greet from "./components/Greet";

function App() {
  return (
    <div className="App">
      <Greet></Greet>
    </div>
  );
}

export default App;

``` 

And on the other hand, a **Stateful Class Component** is implemented as a JavaScript class with state and render. Here the **state** is where we store property values that belong to the component and **render** is to display the specified HTML code inside the specified HTML element.

The structure of a simple stateful class component is as shown below:

``` js 

import React, { Component } from 'react';

class Name extends Component {
    state = {  }
    render() { 
        return (  );
    }
}
 
export default Name;

```

Something to remember that when we render elements there should be one parent element like `<div></div>` as shown below: 

``` js

import React, { Component } from "react";

class Counter extends Component {
  render() {
    return (
      <div>
        <h1>Hello World!</h1>
        <button>Stop helloing me!</button>
      </div>
    );
  }
}

export default Counter;

```
If we don’t want to use `<div></div>` or any other element and we can use `<React.Fragment></React.Fragment>` as parent or just `<></>` will work too . In our **render()** we can call function using **curly brackets** like below :

``` js
<span>{this.justAnotherFunction()}</span>
``` 

Let say we have a **state** where there is **count**. We can use in our code as `this.state.count` or like below :

``` js 

const { count } = this.state;

```

We can implement `styles` in our component by adding property let’s call it **style** like below:

``` js

  style = {
    fontSize: 12,
    fontWeight: "bold",
  };

```

Later we can pass this object in the render:

``` js

<span style={this.style}>
    {this.justAnotherFunction()}
</span>

```

We can also write an inline style like below :

``` js

<span style={{ fontSize: 50, fontWeight: "bold" }}>{this.justAnotherFunction()}</span>

```
___


## JSX

JSX is JavaScript XML which is an extension to the javascript language syntax. It is not mandatory to use JSX in React but it makes our code easier and simpler. A simple **Hello World!** code inside a `h1` tag will be something like this:

``` js

import React from "react";

const Hello = () => {
  return (
    <>
      <h1>Hello World!</h1>
    </>
  );
};

export default Hello;

```
And if we want to recode the component without using JSX. It will look something like this:

``` js

import React from "react";

const Hello = () => {
  return React.createElement(
    "div",
    null,
    React.createElement("h1", null, "Hello World!")
  );
};

export default Hello;

```

In the place of **null** we can assign **class** or **id** using a second bracket eg. `{id : ‘dummyId’ , className:‘dummyClass’}`. 

___

## Props

**Props** include data we give to a component or in a simpler word we pass data from one component to another using **props**. 

So let’s say we want to send my name which is **Sayeem** to a component as props so that it says “Hello Sayeem!”.  There is a component name `Greet`. So first to send my name from the parent **(App.js)** to child **(Greet.js)** like below:

``` js

 <Greet name="Sayeem"></Greet>

```
And in the `Greet.js` we will use the following code to catch the name and print:

``` js

import React from "react";

const Greet = (props) => {
  console.log(props);
  return <h1>Hello {props.name}!</h1>;
};

export default Greet;


``` 

Here we are using curly brackets to print the props. Even we can send and print multiple props like below:

``` js

// App.js

      <Greet name="Sayeem" superheroName="Ironman">
        Just Joking!
      </Greet>

```
``` js

// Greet.js

import React from "react";

const Greet = (props) => {
  console.log(props);
  return (
    <>
      <h1>
        Hello {props.name} a.k.a {props.superheroName}!
      </h1>
      <p>{props.children}</p>
    </>
  );
};

export default Greet;

```

If we want to pass data using props almost everything remains the same but in the child component we have to use the `this` keyword before props eg. this.props.name. 

___

## State

**State** is managed within the component where the variable are not passed but declared in the function body. A state can be changed. In the functional component, a state can be accessed using **useState hooks** and on the other hand **this.state** is used to access in the class components.  
___


## Destructuring Arguments

We can destruct arguments by adding const after **render** and before **return** like below:

``` js

const {onReset , onIncrement , onReset} = this.props;

```

So we don’t need to use **this** every time while using the variables in the code. 

___


## Rendering Lists 

We first initialize a list name `tags` in the `state` which looks like **tags: ["tag1", "tag2", "tag3"]**. We can render it by the following code:

```js
        <ul>
          {this.state.tags.map((tag) => (
            <li key={tag}>{tag}</li>
          ))}
        </ul>
```
Here `key={tag}` is used so that it can be uniquely identified. It shouldn’t have to be unique in the whole component but only on that list. 

___


## Conditional Rendering

We can use logical & operator for conditional rendering like the code below:

``` js

{this.state.tags.length === 0 && "No tags here!"}

```
Here if the length is zero so which makes it true and when the first condition is true it prints the second condition. If there are 3 conditions or more then it will execute the last condition.

___


##   Handling Events & Binding Event Handlers

Let's say we have a button and in click, it will console.log a message like below:

``` js

<button onClick={this.handleIncrement}>Click Here</button>

```
``` js

handleIncrement() {
    console.log("Increment Clicked!");
  }

```

In the above case, there is a problem, we cannot use `this` to use it  we need to bind the event handler like below :

``` js

  constructor() {
    super();
    this.handleIncrement = this.handleIncrement.bind(this);
  }

  handleIncrement() {
    console.log("Increment Clicked!", this);
  }

```

There is another way of doing that, we can simply convert it into an arrow function as it does not rebind `this` function but inherit it. So the code will be like below :

``` js

 handleIncrement = () => {
    console.log("Increment Clicked!", this);
  };

```

___


## Lifecycle Hooks

There are three phases:

* Mounting Phase
* Updating Phase
* Unmounting Phase

#### Mounting Phase

There are three life cycle hooks in this phrase which are `constructor`, `render` and `componentDidMount`. React will call these methods in order. 

##### constructor

When we use `constructor`, we have to call the parent class using `super();` This is called only once when the instance is created. If we want to set **state**, we can’t use `this.setState()`. We have to do like below:

``` js

  constructor(props) {
    super(props);
    this.state = this.props.something; 
  }

```
If we don’t pass `props` as a parameter it will show undefine. 

##### render

It is used to render components in the actual browser DOM.

##### componentDidMount

This method is called after our component is rendered into the DOM. It is a perfect place to use **Ajax** and set state with data.

#### Updating Phase

This phase happens when the props or state of a component is changed. We have two life cycle hooks which are `render` and `componentDidUpdate`.  These two are called in order. 

##### componentDidUpdate

This method is called after a component is updated. In this method, we can make an ajax request to get data from the server and also compare props. 


#### Unmounting Phase

This is the last phase that happens when we remove a component from the DOM such as we delete a counter. We have one life cycle hook which is `componentWillUnmount`. 

###### N.B. We cannot use life cycle hooks in Stateless Functional Component and there are more life cycle hooks but the given ones are most used. 

___


> ##### To get a better understanding we can always give the [React Doc](https://reactjs.org/docs/hello-world.html) a read. 

___



