# Steps followed to create this website

## 1. Create new app using Vite

Use the Vite tool. It creates a boiler plate project for us based on the parameters passed to it.

### Use the following command
`npm create vite@latest xora_sass_app -- --template react`

## 2. Exploring the files created for us by Vite

Everything starts with the `./src/main.jsx`

```
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import App from './App.jsx'
import './index.css'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>,
)
```

The `<App />` component is rendered as the main element.

## 3. Adding Tailwind CSS to our application

Tailwind CSS is a utility-first CSS framework packed with classes like `flex`, `pt-4`, `text-center` and `rotate-90` that can be used to build any design, directly in your HTML. 

To install it with Vite, follow the commands:
1. Install `tailwindcss` and its peer dependencies

   `npm install -D tailwindcss postcss autoprefixer`

2. Generate your `tailwind.config.js` and `postcss.config.js` files

   `npx tailwind init -p`

3. Configure your template paths: Add the paths to all of your template files in your `tailwind.config.js` file.
    ```
    /** @type {import('tailwindcss').Config} */
    export default {
    content: [
        "./index.html",
        "./src/**/*.{js,ts,jsx,tsx}",
    ],
    theme: {
        extend: {},
    },
    plugins: [],
    }
    ```

4. Add the `@tailwind` directives for each of Tailwind's layers to your `./src/index.css` file.
    ```
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
