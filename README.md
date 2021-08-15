# SSR React Playground App
### Ran across this article: https://www.digitalocean.com/community/tutorials/react-server-side-rendering

# Steps
1. Creating the React App and Modifying the App component
    - Use `ReactDOM`'s `hydrate` method instead of `render` [docs](https://reactjs.org/docs/react-dom.html#hydrate)
2. Creating an Express server and Rendering the App Component (simple `GET` endpoint)
    1. Setup the server to serve from `/build` as static files
    2. Utilizes `ReactDOMServer.renderToString` to render `App` to a static HTML string [docs](https://reactjs.org/docs/react-dom-server.html#rendertostring)
    3. Reads our index file via `fs.readFile` and injects our `App`'s static HTML string [fs docs](https://nodejs.org/api/fs.html#fs_fs_readfile_path_options_callback)
    4. Send the response 
3. Config Webpack, Babel, and npm scripts
    1. Create a `.babelrc.json` file to add `env` and `react-app` presets [bebelrc json docs](https://babeljs.io/docs/en/configuration#babelrcjson)
    2. Create a `webpack.server.js` file to output transpiled bundle to `server-build`, use `babel-loader`, and omit files from `node_modules`
    3. Add in scripts to `package.json` to set the env to development, invoke webpack for our server, and nodedemon to serve the build output

