# Next.js 13 E-Commerce Tutorial (App Router, TypeScript, Deployment, TailwindCSS, Prisma, DaisyUI)

## Install Dependencies

1. Install dependencies for daisyui prisma @prisma/client next-auth @auth/prisma-adapter zod

```
yarn add daisyui prisma @prisma/client next-auth @auth/prisma-adapter zod
```

2. Install devdependencies for prettier eslint-config-prettier prettier-plugin-tailwindcss

```
yarn add -D prettier eslint-config-prettier prettier-plugin-tailwindcss @types/eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-import-resolver-typescript eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-hooks
```

## Setup

1. Add daisyui in tailwind.config.ts file

```
plugins: [require("daisyui")],
```

2. Set custom theme in tailwind.config.ts file. e.x:

```
daisyui: {
  themes: [
    {
      lightTheme: {
        primary: "#f4aa3a",
        secondary: "#f4f4a1",
        accent: "#1be885",
        neutral: "#272136",
        "base-100": "#ffffff",
        info: "#778ad4",
        success: "#23b893",
        warning: "#f79926",
        error: "#ea535a",
        body: {
          "background-color": "#e3e6e6",
        },
      },
    },
  ],
},
```

3. Remove unneccessary configuration in global.css. Now we use custom theme on daisyui. Therefore, keep only import files.

4. Setup prettier

5. Create prettier.config.js in root directory
6. Add configuration in prettier.config.js file

```
module.exports = {
  "plugins": ["prettier-plugin-tailwindcss"],
};
```

3. Add prettier in eslint.json file

```
{
  "extends": ["next/core-web-vitals", "prettier"]
}
```

## SEO

1. Add opengraph-image.png file in src/app directory
2. Replace favicon.ico file in src/app directory
3. Add logo.png in src/assets directory
4. Add profile-pic-placeholder.jpg file in src/assets directory

## Setup Prisma

1. Setup Prisma

```
npx prisma init
```

2. Add database url on .env.
3. Update database provider (from postgres to mongodb or others) in schema.prisma file. ex:

```
datasource db {
  provider = "mongodb"
  url      = env("DATABASE_URL")
}
```

4. Setup database on mongo compas

```
ex: name: "Product Name"
```

5. Pull schema from mongodb

```
npx prisma db pull
```

6. If you'd like to format code in schema.prisma, click shift+alt+f

7. After updated schema.prisma file,

```
npx prisma db push
```

8. Create Prisma client

```
npx prisma generate
```

## Prisma Shortkey on MAC

```
shift + alt + f
```
