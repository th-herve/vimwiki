# Javascript using esling and prettier

To use esling and prettier with nvim ale on a project:

1. Install eslint:
    1. npm install eslint --save-dev
    2. Create a config file `.eslintrc.js` or `.eslintrc.json`
    3. Add the config
    ```javascript
    module.exports = {
      env: {
      browser: true,
      node: true,
    },
    extends: ['eslint:recommended'],
    rules: {
    // Add your ESLint rules here
      },
    };
    ```
2. Install prettier:
    1. npm install prettier --save-dev
    2. Create a config file `.prettierrc` or `prettier.config.js`
    3. Add the config
    ```json
    {
      "singleQuote": true,
      "trailingComma": "all",
      "tabWidth": 2,
      "semi": true
    }
    ```
3. Install eslint-config-prettier to make both program work better with each other:
    1. npm install --save-dev eslint-config-prettier
    2. Add `prettier` at the end of the extends array in `.eslintrc`
    ```javascript
    {
      "extends": [
        "some-other-config-you-use",
        "prettier"
      ]
    }
    ```
