# Setting up a new development project

This describes my policies on how to set up a new Node dev project in VS Code to run on Heroku.

## Initialise package.json

Initialise the package.json file by running the following command:

`npm init -y`

Go into the package.json file and add/edit the following code:

1. Set `"main": "app.js"`

2. Set `"engines": { "node": "12.x" } 

3. Set `"scripts": { "start": "node app.js", "dev": "nodemon app.js" }

## Initialise git

Get up git version control on the project by running the following command:

`git init`

1. Create a `.gitignore` file in the root project directory. 

2. Add the following files to `.gitignore`:

  * `node_modules`
  * `.vscode`
  * `.eslintrc.js`
  * `.env`
  * `.DS_Store`
  * `.package-lock.json`

## Set up ESLint

ESLint checks Javascript code against the [Javascript Standards](https://github.com/standard/standard). Implement ESLint with the following process:

1. Install the following npm packages: `npm i -D eslint eslint-config-standard eslint-plugin-import eslint-plugin-node eslint-plugin-promise eslint-plugin-standard`

2. Create `.eslintrc.js` file

3. Add the following code to `.eslintrc.js`: `module.exports = { "extends": "standard" }`

4. Ensure the ESLint extension is added to VS Code

ESLint should now be working.

## Set up Webpack

Webpack is used to bundle assets into a distribution. [Webpack getting started](https://webpack.js.org/guides/getting-started/). 

1. Install the following npm packages: `npm i webpack webpack-cli --save-dev`

2. Create an `src` and `dist` folders

3. Create JS source files in the src folder

4. Add `"private": "true"` to the package.json file

5. Create the file `webpack.config.js` with the following code:
   `const path = require('path')`

`module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist')
  }
}`

6. Add the following script to package.json:

   `"build": "npx webpack --config webpack.config.js"`
