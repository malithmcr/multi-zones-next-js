# Using multiple zones

With Next.js you can use multiple apps as a single app using its [multi-zones feature](https://nextjs.org/docs/advanced-features/multi-zones). This is an example showing how to use it.

- All pages should be unique across zones. For example, the `marketplace` app should not have a `pages/blog/index.js` page.
- The `marketplace` app is the main app and therefore it includes the rewrites that map to the `blog` app in [next.config.js](home/next.config.js)
- The `blog` app sets [`basePath`](https://nextjs.org/docs/api-reference/next.config.js/basepath) to `/blog` so that generated pages, Next.js assets and public assets are within the `/blog` subfolder.

## How to use

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init) or [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/) to bootstrap the example:

```bash
npx create-next-app --example with-zones with-zones-app
# or
yarn create next-app --example with-zones with-zones-app
```

With multi zones you have multiple Next.js apps over a single app, therefore every app has its own dependencies and it runs independently.

To start the `/` run the following commands from the root directory:

```bash
cd marketplace
npm install && npm run dev
# or
cd marketplace
yarn && yarn dev
```

The `/` app should be up and running in [http://localhost:3000](http://localhost:3000)!

Starting the `/blog` app follows a very similar process. In a new terminal, run the following commands from the root directory :

```bash
cd blog
npm install && npm run dev
# or
cd blog
yarn && yarn dev
```

The `blog` app should be up and running in [http://localhost:8080](http://localhost:8080)!
