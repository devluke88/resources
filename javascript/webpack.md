# Webpack

### Start project

```
// Create a new project directory and cd to it
mkdir my-project
cd my-poject

// Generate package.json
npm init

// If you downloading repo from Github all dependencies that are stored in node_modules dir can be installed from your package.json by running the following
npm install

// Install webpack to the node_modules directory
npm install webpack webpack-cli --save-dev

// Create a src and dist directory with the index.js file in src and an index.html file in dist
mkdir src dist
touch src/index.js
touch dist/index.html

// Create a webpack.config.js in the main directory
touch webpack.config.js

// https://webpack.js.org/guides/getting-started/#using-a-configuration
// Add the following to webpack.config.js

const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist'),
  },
};

// Or add the following to also load css file
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      },
      {
        test: /\.(png|svg|jpg|jpeg|gif)$/i,
        type: 'asset/resource',
      },
    ]
  }
};

// Install css-loader and style-loader
npm install --save-dev style-loader css-loader
```

#### Compile files

```
// Compile file, dist/main.js
npx webpack 

// Compile using a given config file
npx webpack --config webpack.config.js

// Compile file, and auto-reload index.html page when you make changes
npx webpack --watch

```

#### Useful resources

{% embed url="https://webpack.js.org/guides/asset-management/" %}
Webpack
{% endembed %}
