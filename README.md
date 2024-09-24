# react-features

## Set Up The Environment

```npx create-react-app name-of-the-react-app```
```npx``` is command that comes with node js, it allows us to run npm packages(Node.js packages) without installing them globally.
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
you get one bundlled file 
```
<script src="bundle.js"></script>
```
2. 