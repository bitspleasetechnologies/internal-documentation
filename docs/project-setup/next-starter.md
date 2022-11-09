# Next.js, Tailwind & Typescript Setup Guide.

This starter guide will help you set up your nextjs project with typescript and tailwind.

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

Then move the `app, pages, public` folder into the `src` folder.

> the `-t, --target-directory=DIRECTORY` flag for the `mv` command moves all SOURCE arguments into DIRECTORY 

```bash
mv -t src app pages public
```

### Typescript Setup

### Tailwind Setup
