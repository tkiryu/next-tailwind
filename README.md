# Minimum setup to use TailwindCSS with Next.js

1. Create Next project

```
npx create-next-app next-tailwind --use-npm
```

2. Install and configure TailwindCSS

```
npm i tailwindcss postcss autoprefixer
```

Then, create `tailwind.config.js` files by `tailwindcss` command with `-p` option.

```
npx tailwindcss init -p
```

Add any files that reference any tailwindcss classes to `purge` option.

```
// tailwind.config.js
module.exports = {
  purge: ['./pages/**/*.{js|jsx}'], // add any files that reference any tailwindcss classes.
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
}
```

```
// No need to change postcss.config.js for now
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

3. Include Tailwind styles in you CSS

```
/* styles/globals.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

That's it!
