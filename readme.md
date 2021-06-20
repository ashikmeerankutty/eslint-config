# Eslint and Prettier Setup

These are my settings for ESLint and Prettier

## Installing

1. Install everything needed by the config:

```
npx install-peerdeps --dev eslint-config-mrdevops
```

2. You can see in your package.json there are now a big list of devDependencies.

3. Create a `.eslintrc` file in the root of your project's directory (it should live where package.json does). Your `.eslintrc` file should look like this:

```json
{
  "extends": ["mrdevops"]
}
```

4. Add scripts to lint and fix:

```json
"scripts": {
  "lint": "eslint .",
  "lint:fix": "eslint . --fix"
},
```

5. Lint your code by running `npm run lint` and fix all fixable issues with `npm run lint:fix`.

## VS Code Settings

1. Install the [ESLint package](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
2. Add these settings to VSCODE `settings.json`

```js
// Auto format on save
"editor.formatOnSave": true,
// turn it off for JS and JSX, we will do this via eslint
"[javascriptreact]": {
  "editor.defaultFormatter": null,
  "editor.formatOnSave": false
},
"[javascript]": {
  "editor.defaultFormatter": null,
  "editor.formatOnSave": false
},
// show eslint icon at bottom toolbar
"eslint.alwaysShowStatus": true,
// tell the ESLint plugin to run on save
"editor.codeActionsOnSave": {
  "source.fixAll": true
}
```
