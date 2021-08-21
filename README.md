# ESLint Learning
ESLint help find and fix problems in your JavaScript code. This tool can be used in React, Vue.js, and other JavaScript project. [Find more information here](https://eslint.org/)

## Installation and Setup
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