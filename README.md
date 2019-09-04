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



