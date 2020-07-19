# svelte bulma template
This is a modified [svelte template](https://github.com/sveltejs/template), to include the bulma css, which is installed through npm.

## how to use
There are three options:
- use the github template feature, to create a new repository based on this codebase
- clone this repository and apply any changes you want+
- follow the steps in [setup](https://github.com/manuel3108/svelte-bulma-template#setup)

## setup
First install bulma and a rollup helper plugin:
```
npm i rollup-plugin-css-only bulma
```

Go to your `rollup.config.js`
and apply the following changes:
```js
import svelte from 'rollup-plugin-svelte';
// ....
import css from "rollup-plugin-css-only";

export default {
	plugins: [
		css({ output: "public/build/extra.css" }),       
        // all other plugins
	]
};
```

Go to your `App.svelte` and import the following:
```js
import 'bulma/css/bulma.css'
```

Go to your `public/index.html` and add this somewhere in your `head`:
```html
<link rel="stylesheet" href="/build/extra.css" />
```

And ther you go!

You should now be able to use something like:
```html
<button class="button">Button</button>
```
Now you should see a nice looking [Bulma Button](https://bulma.io/documentation/elements/button/)
