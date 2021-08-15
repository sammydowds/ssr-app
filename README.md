# SSR React Playground App
### Ran across this article: https://www.digitalocean.com/community/tutorials/react-server-side-rendering

# Steps
1. Creating the React App and Modifying the App component
    - Use `ReactDOM`'s `hydrate` method instead of `render` [docs](https://reactjs.org/docs/react-dom.html#hydrate)
2. Creating an Express server and Rendering the App Component (simple `GET` endpoint)
    1. Setup the server to serve from `/build` as static files
    2. Utilizes `ReactDOMServer.renderToString` to render `App` to a static HTML string [docs](https://reactjs.org/docs/react-dom-server.html#rendertostring)
    3. Reads our index file via `fs.readFile` and injects our `Apps` static HTML string
    4. end the response 
3. Config Webpack, Babel, and npm scripts
    1. Create a `.babelrc.json` file to add `env` and `react-app` presets
    2. Create a `webpack.server.js` file to output to `server-build` and omit files from `node_modules`
    3. Add in scripts to `package.json` to set the env to development, invoke webpack for our server, and nodedemon to serve the build output

