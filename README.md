# Mark Hkr Eslint and Remix TS Setup
My settings for ESLint and Remix TS

## What it does
* Lints JavaScript based on the latest standards
* Lints + Fixes inside of html script tags
* You can see all the [rules here](https://github.com/markhker/eslint-config-markhkr-remix-ts/blob/master/.eslintrc.js)

## Installing

You can use eslint globally and/or locally per project.

## Local / Per Project Install

1. If you don't already have a `package.json` file, create one with `yarn init` or `npm init`.

2. Create a `.eslintrc` file in the root of your project's directory (it should live where package.json does). Your `.eslintrc` file should look like this:

```json
{
  "extends": [
    "markhkr"
  ]
}
```

3. You can add two scripts to your package.json to lint and/or fix:

```json
"scripts": {
  "lint": "eslint .",
  "lint:fix": "eslint . --fix"
},
```

4. Now you can manually lint your code by running `npm run lint` and fix all fixable issues with `npm run lint:fix`.

## Settings

If you'd like to overwrite eslint settings, you can add the rules in your `.eslintrc` file. The [ESLint rules](https://eslint.org/docs/rules/) go directly under `"rules"`.

```js
{
  "extends": [
    "markhkr"
  ],
  "rules": {
    "no-console": 2,
  }
}
```

## With VS Code

Once you have done the install. You probably want your editor to lint and fix for you. Here are the instructions for VS Code:

1. Install the [ESLint package](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
2. Now we need to setup some VS Code settings via `Code/File` → `Preferences` → `Settings`. It's easier to enter these settings while editing the `settings.json` file, so click the Open (Open Settings) icon in the top right corner:

  ```js
  // These are all my auto-save configs
  "editor.formatOnSave": true,
  // turn it off for JS and JSX, we will do this via eslint
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false
  },
  // show eslint icon at bottom toolbar
  "eslint.alwaysShowStatus": true,
  // tell the ESLint plugin to run on save
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  },
  ```

After attempting to lint your file for the first time, you may need to click on 'ESLint' in the bottom right and select 'Allow Everywhere' in the alert window.

Finally you'll usually need to restart VS code. They say you don't need to, but it's never worked for me until I restart.


## With Yarn

It should just work, but if they aren't showing up in your package.json, try `npx install-peerdeps --dev eslint-config-markhkr -Y`
