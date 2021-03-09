# React-Cribsheet

> React is a **JavaScript library** for building User interfaces(UI). The heart of React application is component. Component is a piece of UI. A tree of components makes a complete UI. In the root of the tree is the main component (App). A component is implemented as a JavaScript class with some states and render. So after [CSS Cribsheet](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md) this is another initiative to make small notes on React which may help me or anyone else in the future. 


Before starting React we have to download and install **Node js** and **NPM**. If we use Linux, we can use the following commands :

``` shell

$ sudo apt install nodejs
$ sudo apt install npm

```

After that we can use the below command to install package which will create react app:

``` shell

$sudo npm i -g create-react-app

```

I used `create-react-app@4.0.3`.We can use [Visual Studio Code](https://code.visualstudio.com/) as our code editor. Inside [Visual Studio Code](https://code.visualstudio.com/) we can install [Prettier - Code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) formatter to make our code prettier and easier to read/debug and [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets) for snippets of usable React codes.


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

After starting our project we will see **node_modules** which there are 3rd party libraries and react itselves, **public** for public assets and **src** for basic components. 

To see the conversion of modern javascript to browser-compatible JavaScript we can use [Babel](https://babeljs.io/).


___

## Hello World!

To print **“Hello World!”** in our screen we can write the following code:

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

`let` is used to assign value to variables in a block which cannot be accessed outside.

#### var

`var` is used to assign value to variables which can be accessed anywhere.

#### const

`const` is used to assign value to variables which cannot be re-assigned anywhere in the code.

#### Objects

Objects are collections of key value pairs. We can make an object like below:

``` js

const person = {
    name: 'Sayeem',
    walk(){},
    run(){}
};

```

To access the members we can use `person.talk()` or `person[‘name’] = ‘Abdullah’`. 

#### this

`this` is a keyword in JavaScript which doesn’t behave same as C# or Java. The value of `this` is determined by how a function is called. If it is called as a method in an object it will return the reference to that object and if it's called outside of an object it will return the global object or window object.

If we want to fix that we can use bind function so that we get reference everytime like below: 

``` js

const walk = person.walk.bind(person);

``` 

#### Arrow Functions

We have used function like below before:

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

The above code is pretty self explanatory. 

___

