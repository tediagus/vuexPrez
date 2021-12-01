---
layout: two-cols
---
## Les modules

Permet de diviser le store en plusieurs petites parties


**Structure du store :**
```js 
store/
    ├── index.js    ---> Main Store file
    └── modules/
        ├── module1.store.js
        ├── module2.store.js
        ├── module3.store.js
        ├── module4.store.js
        ├── module5.store.js
        └── module6.store.js
```

**Combiner les modules:**
```js 
/** store/index.js **/
import Vue from 'vue';
import Vuex from 'vuex';
import createLogger from 'vuex/dist/logger';
import Module1 from './modules/module1.store';
import Module2 from './modules/module2.store';
...
Vue.use(Vuex);
const debug = process.env.NODE_ENV !== 'production';
export default new Vuex.Store({
  modules: {
    Module1,
    Module2,
    ...
  },
  strict: debug,
  plugins: debug? [ createLogger() ] : [],
})
```

**Auto importing store modules :**
```js 
store/
   ├── index.js    ---> Main Store file
   └── modules/
       ├── index.js   --> Auto exporter
       ├── module1.store.js
       └── module2.store.js
```


**Auto export script :**
```
/**
* Automatically imports all the modules and exports as a single module object
  */
  const requireModule = require.context('.', false,  /\.store\.js$/);
  const modules = {};

requireModule.keys().forEach(filename => {

    // create the module name from fileName
    // remove the store.js extension and capitalize
    const moduleName = filename
                   .replace(/(\.\/|\.store\.js)/g, '')
                   .replace(/^\w/, c => c.toUpperCase())

    modules[moduleName] = requireModule(filename).default || requireModule(filename);
});

export default modules;
```

**store/index.js final :**
```
import Vue from 'vue'
import Vuex from 'vuex'
import createLogger from 'vuex/dist/logger'

// import the auto exporter
import modules from './modules';

Vue.use(Vuex);
const debug = process.env.NODE_ENV !== 'production';

export default new Vuex.Store({
modules, // all your modules automatically imported :)
strict: debug,
plugins: debug ? [createLogger()] : [] // set logger only for development
})
```