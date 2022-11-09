# Next.js, Tailwind & Typescript Setup Guide.

!!! warning "Using these command line tools requires eigher a unix based system or [git bash](https://git-scm.com/download/win) on Windows."

This starter guide will help you set up your nextjs project with typescript and tailwind.

![Bits Please Logo](../images/logo.png)

## Installation

### Next Setup

Create a new next project with the create-next-app script and yarn.

> while the `/app` folder is in beta.

```bash
  yarn create next-app my-project --ts --eslint --experimental-app
```

> after the `/app` folder is out of beta.

```bash
  yarn create next-app my-project --ts --eslint
```

After you've created your next project make a `src` folder in the root of your project.

```bash
mkdir src
```

Then move the `app,pages` folders into the `src` folder.

> the `-t, --target-directory=DIRECTORY` flag for the `mv` command moves all SOURCE arguments into DIRECTORY

```bash
mv -t src app pages
```

After you've moved these folders to the `src` folder root of your project. Navigate into the directory and create these folders and add placeholder files. `eg. hooks/hooks.placeholder`

> We will remove the placeholder files when we start using the directories.

```
src/
├─ config/
├─ hooks/
├─ interfaces/
├─ services/
├─ utils/
```

```bash
cd src
mkdir config hooks interfaces services utils
touch config/congig.placeholder hooks/hooks.placeholder interfaces/interfaces.placeholder services/services.placeholder utils/utils.placeholder
```

### Typescript Setup

### Tailwind Setup

!!! note "By the time you're reading this the documentation of this section may have been changed. [click here](https://tailwindcss.com/docs/guides/nextjs) to checkout the latest version."

Start by adding the tailwind dependencies and initialize the tailwind configuration.

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Add the paths to all of your template files in your tailwind.config.js file.

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx}",
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Add the `@tailwind` directives for each of Tailwind’s layers to your `./styles/globals.css` file.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Start your build process.

```bash
yarn run dev
```
