
#### Tips pour combiner les modules automatiquement

<div class="grid grid-cols-2 gap-4">
<div>

**Script**
```js 
/** store/modules/index.js **/
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

</div>
<div>

**Magie**
```js
/** store/index.js **/
import Vue from 'vue'
import Vuex from 'vuex'
import createLogger from 'vuex/dist/logger'

// import the auto exporter
import modules from './modules';

Vue.use(Vuex);
const debug = process.env.NODE_ENV !== 'production'

export default new Vuex.Store({
modules, // all your modules automatically imported :)
strict: debug,
plugins: debug ? [createLogger()] : []
})
```

</div>
</div>

<!--
- For example, if you have a file named user.store.js this will be imported as a store module name-spaced as User.

- Best practice : We need to make sure each module is name-spaced and not to access them using the global store scope.
-->
