---
layout: post
title: Ant Design Pro(2): create-umi
date: 2020-03-02 11:23
post-link: https://dvajs.com/
---

In the past, `dva-cli` was the app responsible for setting up projects from scratch. This has now been deprecated, and the same task is accomplished by `create-umi`:

```
yarn create umi <app-name>
```

Then to start the development server, we just:

```
yarn
yarn start
```

The project structure is mostly the same as `dva`.

```
.
├── config
├── mock
├── public
│   └── icons
├── src
│   ├── assets
│   ├── components
│   ├── e2e
│   ├── layouts
│   ├── locales
│   ├── models
│   ├── pages
│   ├── services
│   └── utils
└── tests
```

The structure is fairly straight forward, but let me go into it a bit just for clarity's sake:

- `./config/` is where configuration files live, naturally.
- `./mock/` you have three guesses.
- `./public/` is where static files live that are accessed by pathname and not internally by React as assets.
- `./src/assets` is where static files used by React live, with the exception of stylesheets (although that's just a convention).
- `./src/components` another three guesses.
- `./src/e2e` no idea.
- `./src/layouts`. This is a special folder only for container components, which are called Layouts in the Ant Design world.
- `./src/locales` more three guesses.
- `./src/models` more three guesses
- `./src/pages/` is where the actual pages live. This one of the more opinionated aspects about `umi`, that it does routing like `php`, `next.js` or `jekyll` do routing, i.e. the folder path undr pages maps directly to the url path. This is the opposite of the dynamic routing that you get with `react-router`. In an older version of `dva` this folder was called `routes` but I guess they changed it.
- `./src/services` this is where async reducers live, which are handled by `dva`, which itelf just wraps `react-sagas`.
- `./src/utils` is for utility/helper functions.
