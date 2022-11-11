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

```
src/
├─ config/
├─ hooks/
├─ interfaces/
├─ services/
├─ utils/
```

> We will remove the placeholder files when we start using the directories.

```bash
# naviagete to `src` directory
cd src

# make tconfig hooks interfaces services utils directories
mkdir components config hooks interfaces services utils

# add placeholder files to directories
touch components/components.placeholder config/config.placeholder hooks/hooks.placeholder interfaces/interfaces.placeholder services/services.placeholder utils/utils.placeholder
```

### Typescript Setup

Open your "tsconfig.json" file and add the following lines to your `compilerOptions` object:

```json
{
  "compilerOptions": {
    ...
    "incremental": true,
    /* --- start copy here --- */
    "baseUrl": "src",
    "paths": {
      "@components/*": ["components/*"],
      "@config/*": ["config/*"],
      "@hooks/*": ["hooks/*"],
      "@interfaces/*": ["components/*"],
      "@services/*": ["services/*"],
      "@styles/*": ["styles/*"],
      "@images/*": ["assets/images/*"]
    },
    /* --- end copy here ---*/
      "plugins": [...],
  },
  ...
}
```

### Tailwind Setup

!!! note "By the time you're reading this the documentation of this section may have been changed. [click here](https://tailwindcss.com/docs/guides/nextjs) to checkout the latest version."

Start by adding the tailwind dependencies and initialize the tailwind configuration.

```bash
yarn add -D tailwindcss postcss autoprefixer
yarn tailwindcss init -p
```

Add the paths to all of your template files in your `tailwind.config.js` file.

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/app/**/*.{js,ts,jsx,tsx}",
    "./src/pages/**/*.{js,ts,jsx,tsx}",
    "./src/components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Add the `@tailwind` directives for each of Tailwind’s layers to your `app/globals.css` file.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Configure your tailwind configuration to the needs of pojected templates

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/app/**/*.{js,ts,jsx,tsx}",
    "./src/pages/**/*.{js,ts,jsx,tsx}",
    "./src/components/**/*.{js,ts,jsx,tsx}"
    ]
  theme: {
    /* you can choose to override the default theme */
    fontFamily: {
      ...
    },
    fontSize: {
     ...
    },
    /* or you can choose to extend the default theme */
    extend: {
      backgroundImage: {
       ...
      },
      colors: {
       ...
      },
      screens: {
       ...
      },
      gridAutoColumns: {
       ...
      }
    },
  },
  plugins: [],
};


```

Start your build process.

```bash
yarn run dev
```
