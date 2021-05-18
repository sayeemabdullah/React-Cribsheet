# React-Cribsheet

> React is a **JavaScript library** for building User interfaces(UI). So after [CSS Cribsheet](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md) this is another initiative to make small notes on React which may help me or anyone else in the future. 


Before starting React we have to download and install **Node js** and **NPM**. If we use Linux, we can use the following commands :

``` shell

$ sudo apt install nodejs
$ sudo apt install npm

```

After that we can use the below command to install the package which will create react app:

``` shell

$sudo npm i -g create-react-app

```

I used `create-react-app@4.0.3`.We can use [Visual Studio Code](https://code.visualstudio.com/) as our code editor. Inside [Visual Studio Code](https://code.visualstudio.com/) we can install [Prettier - Code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) formatter to make our code prettier and easier to read/debug and [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets) for snippets of usable React codes.

___

## Context Table

|Topics|
|---|
|[Creating & Starting Application](https://github.com/sayeemabdullah/React-Cribsheet#creating--starting-application)|
|[How things works?](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#how-things-works)|
|[Hello World!](https://github.com/sayeemabdullah/React-Cribsheet#hello-world)|
|[ES6](https://github.com/sayeemabdullah/React-Cribsheet#es6)|
|[Adding Bootstrap](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#adding-bootstrap)|
|[Components](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#components)|
|[Composing Components](https://github.com/sayeemabdullah/React-Cribsheet/blob/main/README.md#composing-components)|
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

$ npx create-react-app react-app

```

And now to start our project we will use the following command after going to our project directory which is **react-app** for me:

``` shell

$ npm start

```

**npm** is for package and dependency management and **npx** is for project management.

After starting our project we will see **node_modules** which there are 3rd party libraries and react itself, **public** for public assets and **src** for basic components. 

To see the conversion of modern javascript to browser-compatible JavaScript we can use [Babel](https://babeljs.io/).

___

## How things works?

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

So here it throws all the things inside **App** component to the div whose id is root. Now inside `App.js` file we can add more components or write code there which will be rendered accordingly. 

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

To access the members we can use `person.talk()` or `person[‘name’] = ‘Abdullah’`. 

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

Stateless Functional Component
Stateful Class Component

A **Stateless Functional Component** is just another javascript function and on the other hand, a **Stateful Class Component** is implemented as a JavaScript class with state and render. Here the **state** is where we store property values that belong to the component and **render** is to display the specified HTML code inside the specified HTML element.

The structure of a simple stateful class component is like below:

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

Something to remember that when we render elements there should be one parent element like `html <div></div>` as shown below: 

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
If we don’t want to use `<div></div>` or any other element we can use `<React.Fragment></React.Fragment>` as parent. In our **render()** we can call function using **curly brackets** like below :

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

#### Rendering Lists 

We first initialize a list name `tags` in the `state` which looks like **tags: ["tag1", "tag2", "tag3"]**. We can render it by the following code:

```js
<ul>
          {this.state.tags.map((tag) => (
            <li key={tag}>{tag}</li>
          ))}
        </ul>
```
Here `key={tag}` is used so that it can be uniquely identified. It shouldn’t have to be unique in the whole component but only on that list. 

#### Conditional Rendering

We can use logical & operator for conditional rendering like the code below:

``` js

{this.state.tags.length === 0 && "No tags here!"}

```
Here if the length is zero so which makes it true and when the first condition is true it prints the second condition. If there are 3 conditions or more then it will execute the last condition.


####   Handling Events & Binding Event Handlers

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

#### Passing Event Arguments

We can pass event arguments using the following code:


``` js

<button onClick={() => this.handleIncrement({ id: 1 })} > </button> 

```

``` js

  handleIncrement = (product) => {
    console.log(product);
    this.setState({ count: this.state.count + 1 });
  };

```
In the place of `id : 1`, we can pass any parameter we want. 
___


## Composing Components

#### Passing Data to Components

We can pass data from one React component to another component using **props**. Let’s say we have a table in a component as shown below : 

``` js
// counters.jsx

import Counter from "./counter";
```
``` js
// counters.jsx

{this.state.counters.map((counter) => (
            <Counter
              key={counter.id}
              value={counter.value}
              selected={true}
            ></Counter>
))}

```

We want to use `value` in another component name `counter.jsx`. If we want to use the values in the state we can use the following code :  

``` js

// counter.jsx

state = {
    value: this.props.value,
  };

```

#### Props vs State

**Props** include data we give to a component and **State** include data that is local or private to the component. React does not allow us to modify any object in the props where State can be modified but only by the component which owns it. 

#### Raising and Handling Events

Let’s say in `counter.jsx` there is a **button** that will **delete** a **value** from the **state** which is in `counters.jsx`. To do so we have to use `props` like below: 

``` js

// counters.js

handleDelete = () => {
   // Code here
  };

  render() {
    return (
      <>
        <div>
          {this.state.counters.map((counter) => (
            <Counter
              key={counter.id}
              id={counter.id}
              value={counter.value}
              selected={true}
              onDelete={this.handleDelete}
            ></Counter>
          ))}
        </div>
      </>
    );
  }

```
``` js

// counter.jsx

<button onClick={() => this.props.onDelete()}>Button</button>

```
#### Updating the State

To update the state we can use the following code:

``` js
 
 handleDelete = (counterId) => {
    const counters = this.state.counters.filter((c) => c.id !== counterId);
    this.setState({ counters });
  };

```

#### Controlled Component:

A component that **does not have its local state** so it **receives data by props** and **raises events whenever data need to be changed**.

#### Stateless Functional Components

We can make components with function in the place of class. If we want to use props we have to pass it as a parameter. It will be something like this :

``` js

const NavBar = (props) => {
  return (
    <nav className="navbar navbar-light bg-light">
      <a className="navbar-brand" href="#">
        Navbar{" "}
        <span className="badge badge-pill badge-secondary">
          {props.totalCounters}
        </span>
      </a>
    </nav>
  );
};

```

#### Destructuring Arguments

We can destruct arguments without using `props`. By adding const after **render** and before **return** like below:

``` js

const {onReset , onIncrement , onReset} = this.props;

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


## To get a better understanding we can always give the [React Doc](https://reactjs.org/docs/hello-world.html) a read. 

___
