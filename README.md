# Install Tailwind CSS with React, Vite and Typescript.

## 1 - Create your Project

Start by creating a new Vite project if you don’t have one set up already.
I personally use the command `npm create vite@latest` and just follow the steps to create a React project with Typescript

```
npm run dev
```


## 2 - Install Tailwind CSS
Install Tailwind CSS and its peer dependencies via npm, and then run the init command to generate both `tailwind.config.js` and `postcss.config.js`.

```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```


## 2.5 - Organize the files
That's an optional step. Now, I just organize the folders and delete the files that I don't need.
I usually start all my projects with the same structure, so that's the moment where I clean some folders and write a friendly 'Hello, world!'.


## 3 - Add Tailwind to your PostCSS configuration
Create the `postcss.config.js` file and add tailwindcss and autoprefixer to it.

```
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```


## 4 - Configure your template paths
On your `tailwind.config.css` file, add the paths to all of your template files.

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["*"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```


## 5 - Add the Tailwind directives to your CSS
On your global css file, add the @tailwind directives for each of Tailwind’s layers.
(I usually create a 'styles' folder and create a `global.css` file inside).

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```


## 6 - Import the CSS file
Import the newly-created `./src/styles/global.css` file in your `./src/main.tsx file`.

```
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './components/App/App'

import './styles/global.css'

ReactDOM.createRoot(document.getElementById('root') as HTMLElement).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)
```


## 7 - Install Node Modules again
For some reason that I can't explain (yet), on the latest version of Vite if you try to run `npm run dev` at this point it won't work and you'll see an error.
So, the solution for this is delete 'node_modules' folder and then run `npm install` to install the modules again.


## 8 - Start your build process
Finally, run your build process with `npm run dev`.

```
npm run dev
```


## :heavy_check_mark: It's done! Start using Tailwind’s utility classes to style your project.

<img width="300" src="https://raw.githubusercontent.com/ldequadra/vite-tailwind/main/Horizontal-Color.svg" alt="ldequadra-horizontal-color">
