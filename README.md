# react-features

## Set Up The Environment

```npx create-react-app name-of-the-react-app```
```npx``` is command that comes with node js, it allows us to run npm packages(Node.js packages) without installing them globally (it's js package executer used to execute the js packages directly without installing them).
in this case it is used to rub the create-react-app package
```create-react-app``` tool developped by the react team to help us quickly set up new React project, it automatically configures the react project with everything we need.
it set up :
1. Webpack
which it's a tool that bundles (the process of taking multiple files and combining them into a single or a few larger files) **why bundling is important >** bcs modern web apps have many js files css , images etc.. if the browser had to request each file individually, it would slow down the app. this was for a performance purpose, also the manification when bundling, the files are minified (unnecessery characters like spaces are removed) to reduce the size of the file and speeding up loading time.
for example instead of loading multiple separate JavaScript modules: :
```
<script src="index.js"></script>
<script src="app.js"></script>
<script src="helpers.js"></script>
```
you get one bundlled file :
```
<script src="bundle.js"></script>
```
2. Babel
which is the js compiler that converts modern js (ES6+) into older js that browsers can understand, bcs not all the browsers supports the latests js features, and it is automatically set up to handle JSX and modern js features so the **compatibility is not an issue anymore**.

3. Development Server
the development server is a tool that runs your app on your local machine so u can see changes in real-time while coding, it automatically reloads the app in the browser every time there is a save to changes.

now the app will be created locally and we can start it using 
```
npm start
```
which it is a package manager used to install, delete and update js packages on the machine.

## exploring the project structure

```src/index.js```: this is the entry point of the React application, it imports the root component and renders it to the DOM
```src/App.js```: this file contains the root component of the application, we can start building the UI in this component or create another components and use them here
```src/components/``` : this folder is where we can store the reusable components
```public/index.html```: this file is the base HTML template for the react app, the entry point of the app (src/index.js) will be included here

## Some basics
- State: the use of React state to handle and update data in the app
- Routing: seting up a routing in the app using React router to create a route-based navigation.
- API Calls: Connect to a backend API and make HTTP calls using libraries like Axios or Fetch
- Styling: Add styles to the components using CSS, Sass or inline styling libraries like styled-components.

<!-- ## Start with functional Components -->
## Build my own React

int Java script the word **Document** is an object represents the entire HTML document that is currently loaded in the browser.
it's part of the Document Object Model DOM which provides a structured representation as a tree of *objects* 
as conclusion the **Document** object is the root node of the DOM tree.

- document.getElementById(id): Retrieves an element by its ID.
- document.getElementsByClassName(name): Retrieves elements by their class name.
- document.querySelector(selector): Retrieves the first element that matches a specified CSS selector.
- document.URL: Returns the URL of the document.
- document.title: Gets or sets the title of the document.
- document.body: Returns the <body> element of the document.
- document.head: Returns the <head> element of the document.

what really happens when we do this document.get... and assign it to a variable like let *test*, test will contain a refrence to that element if it exists else *null*

*getElementById* *getElementsByClassName* *querySelector* these methods are part of the object document once we call them they do their jobs.

*URL* *title* *body* *head* and thes are properties of the object document, once the object is created they have a default values and we can change them in case we need that.

in JavaScript the Document object is part of the browser's DOM and is not created by the developers, it's automatically instantiated by the browser once the the HTML document is loaded.
here an exemple that can demonstrate how all this works
i'll create a **Document** class and from it we gonna instanciate an object like the document object
for example :
```
Class Element
{
    constructor(tagName)
    {
        this.tagName = tagName;
        this.children = [];
        this.innerHtml = '';
    }
    appendChild(child)
    {
        this.children.push(child);
    }

    toString()
    {
        return (
            '
                <${this.tagName}>
                    ${this.innerHtml}
                    ${this....}
                </${this.tagName}>
            ';
        )
    }
}

Class Document
{
    constructor()
    {
        this.title = 'untitled document';
        this.body = new Element('body');
        this.head = new Element('head');
        this.url = 'https://exemple.com';
    }
    setTitle(newTitle)
    {
        this.title = newTitle;
    }
    getTitle()
    {
        return (this.title);
    }
    createElement(tagName)
    {
        return (new Element(tagName));
    }
    getElementById(id)
    {
        // for simplicity, i will not implement a full search
        return(
            this.body.children.find(child => child.id === id || null);
        )
    }
}

const myDocument = new Document();
myDocument.setTitle('my document');

const header = myDocument.createElement('h1);
header.innerHTML = 'Hello Word';
myDocument.body.appendChild(header)

```