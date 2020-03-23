---
layout: post
title: Setup Ant Design
date: 2020-01-20 11:23
post-link: https://ant.design/docs/react/introduce
---

Ant Design is probably my favourite UI library. It is developed by Alibaba and used in basically all big apps in China (this is also why they all look the same). 

Setting up Ant Design with named imports and tree shaking has been greatly simplified in v4:

 First of all, you will need `yarn`, so install that somehow (tip: Google can help if you don't know how).
 
```
yarn create react-app antd-demo
cd antd-demo
yarn add antd
```

Now we could start using the thing, but we would not get tree shaking. To get tree shaking we need to change the webpack config. There's some tooling for that as well...
```
yarn add react-app-rewired customize-cra
```

Now edit the scripts in `package.json` so they use react-app-rewired instead of react-scripts:

```
/* package.json */
"scripts": {
   "start": "react-app-rewired start",
   "build": "react-app-rewired build",
   "test": "react-app-rewired test",
}
```

More tooling:

```
yarn add babel-plugin-import
```

Almost there, we need to create a `config-overrides.js` file and paste this in:

```
const { override, fixBabelImports } = require('customize-cra');

module.exports = override(
  fixBabelImports('import', {
    libraryName: 'antd',
    libraryDirectory: 'es',
    style: 'css',
  }),
);
```

Now we can start using the library with tree shaking. Here's an example:

```
import React, { Component } from 'react';
import { Button } from 'antd';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <Button type="primary">Button</Button>
      </div>
    );
  }
}

export default App;
```

Then run the start command with `yarn` or `npm`:

```
yarn start
```

The workflow with these libraries is always the same. Instead of writing components for scratch, we copy the code from the docs. Then we can customize the component by passing in styles.
