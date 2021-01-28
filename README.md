# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

"# e-commace-site-using-React-2021" 


### You can check that both are installed correctly by issuing the following commands from the command line:
   node -v
> 12.18.4

npm -v
> 6.14.8 `

###  With that done, let’s start off by creating a new React project with the `Create React App tool`. You can either install this globally, or use npx, like so:

` npx create-react-app e-commerce `

### When this has finished, change into the newly created directory:

`cd e-commerce`

### In this application, we’ll use React Router to handle the routing. To install this module, run:

`npm install react-router-dom`

### We’ll also need json-server and json-server-auth to create our fake back end to handle authentication:

`npm install json-server json-server-auth `

### We’ll need axios for making Ajax requests to our fake back end.
` npm install axios `

### And we’ll need jwt-decode so that we can parse the JWT that our back end will respond with:
` npm install jwt-decode `

### Finally, we’ll use the Bulma CSS framework to style this application. To install this, run the following command:
`npm install bulma `

## Getting Started
First, we need to add the stylesheet to our application. To achieve this, we’ll add an import statement to include this file in the `index.js` file in the `src` folder. This will apply the style sheet across all the components in the application:

`import "bulma/css/bulma.css";`

### Context Setup
As previously mentioned, we’ll be using React Context throughout our app. This is a relatively new addition to React and provides a way to pass data through the component tree without having to pass props down manually at every level.

In order to create the context, we create a Context.js file and a withContext.js files in our app’s src directory:
Then add the following to `Context.js` :
```
import React from "react";
const Context = React.createContext({});
export default Context;
```
This creates the context and initializes the context data to an empty object. Next, we need to create a component wrapper, which we’ll use to wrap components that use the context data and methods:
```
// src/withContext.js

import React from "react";
import Context from "./Context";

const withContext = WrappedComponent => {
  const WithHOC = props => {
    return (
      <Context.Consumer>
        {context => <WrappedComponent {...props} context={context} />}
      </Context.Consumer>
    );
  };

  return WithHOC;
};

export default withContext;
```

