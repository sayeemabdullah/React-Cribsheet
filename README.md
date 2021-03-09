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

