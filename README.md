# Prettier and Linter Learning

## Prettier vs Linters

1. Formatting rules: eg: keyword-spacing, comma-style and more. Prettier alleviates the need for this whole category of rules.
2. Code-quality rules: eg: no-unused-vars, no-implicit-globals and more. Prettier does nothing to help with those kind of rules. So you have to use Linter to catch the bugs and control code-quality.

## ESLint

ESLint help check syntax, enforce code style and find & fix problems in your JavaScript code. This tool can be used in React, Vue.js, and other JavaScript project. [Find more information here](https://eslint.org/)

### Installation and Setup

1. Use `npm install eslint --save-dev` to install
2. setup Eslint by `npx eslint --init` and select the options

   - How would you like to use ESLint?
     - To check syntax only
     - To check syntax and find problems
     - To check syntax, find problems, and enforce code style
   - What type of modules does your project use?
     - JavaScript modules (import/export)
     - CommonJS (require/exports)
     - None of these
   - Which framework does your project use?
     - React
     - Vue.js
     - None of these
   - Does your project use TypeScript?
     - No
     - Yes
   - Where does your code run?
     - Browser
     - Node
   - (in case of enforce code style) How would you like to define a style for your project?
     - Use a popular style guide (choose Airbnb, Standard, Google and XO)
     - Answer questions about your style
     - Inspect your JavaScript file(s)
   - What format do you want your config file to be in?
     - JavaScript
     - YAML
     - JSON

   ### The results file (JSON format)

   ```JSON
   {
       "env": {
           "browser": true,
           "es2021": true
       },
       "extends": "eslint:recommended",
       "parserOptions": {
           "ecmaVersion": 12,
           "sourceType": "module"
       },
       // custom rules
       "rules": {
       }
   }
   ```

3. In package.json, add new script for running ESLint
   ```JSON
   "scripts": {
       "lint": "eslint src"
   },
   ```
4. Run `npm run lint` to run ESLint. It will shows the problem when your code is not follow the ESLint rules. On the other hand, it will not shows anything if you code is follow the rules.

### Using ESLint in an editor

You can enforce code style in development process before building your project or check with `npm run lint`. In most editor, they have an ESLint extension that can format your code following ESLint rules such as VSCode, Atom and Sublime.

### Ignore some problem showing up in ESLint

- ignore console log

```javascript
const text = 'hello world'
console.log(text) // eslint-disable-line no-console
```

### Use ESLint to format code

ESLint can also format your code like prettier by using `.eslintrc`. More information here

### Problems found in ESLint

1. Expected linebreaks to be 'LF' but found 'CRLF'

   Reason: [enforce consistent linebreak style (linebreak-style) Problem](https://eslint.org/docs/rules/linebreak-style)

   - "unix" (default) enforces the usage of Unix line endings: \n for LF.
   - "windows" enforces the usage of Windows line endings: \r\n for CRLF.
     How to fix: open Settings -> File: Eol -> edit from auto to \n or LF.

## Prettier

You can use Prettier to format code with vscode extension. However, you can format your code just within vscode.

### Install prettier package

```
npm install --save-dev --save-exact prettier
```

### Create config file

In order to set up Prettier in the project, create `.prettierrc`

```javascript
{
  "trailingComma": "es5",
  "printWidth": 80,
  "singleQuote": true
}
```

### Format code

There are two ways to format code:

1. use `npx prettier --write .` command
2. install prettier extension in your editor
