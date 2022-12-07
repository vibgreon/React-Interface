# React-Interface
Hooks Basic Use Cases

This repository has 2 branches, switch to the other one and follow the Readme.md file.

**I've attached the deployed link in the description.**

# React.js: Building an Interface
- **creating react app** using create-react-app
```
npx create-react-app appname
```

## Modifying the installed folder
- **customizing the install** by removing files which will not be used
- mine after clean-up:
![file structure](./after%20customizing%20installation.png)

## Importing Expernal packages
### React Icons
- **react icons**, external package to add icons as dependencies
```
npm install react-icons --save
```
- visit `https://react-icons.github.io/react-icons` for more details on how to use them

### TailwindCSS
- **tailwind css** great for react
```
- npm install -D tailwindcss postcss autoprefixer
- npx tailwindcss init -p
```
- also add tailwind css forms
```
npm install -D @tailwindcss/forms
```
- and add plugin to `tailwind.config.js` file
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [
    require('@tailwindcss/forms'),
  ],
}

```
- Add the @tailwind directives for each of Tailwind’s layers to your `./src/index.css` file.
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
-----------------------------------------------------------------------------------------------------------------
**NOTE**: Now we dont need craco (DON'T NEED TO DO THESE)
#### CRACO (X)
- since create-react-app support postcss8, we need to install **craco** (Create ReactApp Configuration Override)
```
npm i -D @craco/craco
```
- create a CRACO configuration file in your project's root directory and configure:
```
  my-app
  ├── node_modules
+ ├── craco.config.js
  └── package.json
```
- add add this under `craco.config.js`:
```
module.exports = {
    style: {
        postcss: {
            plugins: [
                require('tailwindcss'),
                require('autoprefixer'),
            ],
        },
    },
}
```
- update the existing calls to react-scripts in the `scripts` section of your `package.json` to use the craco CLI:
```
"scripts": {
-  "start": "react-scripts start"
+  "start": "craco start"
-  "build": "react-scripts build"
+  "build": "craco build"
-  "test": "react-scripts test"
+  "test": "craco test"
}
```
-----------------------------------------------------------------------------------------------------------------
