---
layout: full
---

# Les modules

Permet de diviser le store en plusieurs petites parties

<div class="grid grid-cols-2 gap-4">
<div>

**Structure du store**
```js 
store/
    ├── index.js    ---> Main Store file
    └── modules/
        ├── index.js   --> Auto exporter
        ├── module1.store.js
        ├── module2.store.js
        ├── module3.store.js
```

</div>
<div>

**Combiner les modules (classiquement)**

```js 
/** store/index.js **/
import Vue from 'vue';
import Vuex from 'vuex';
import createLogger from 'vuex/dist/logger';
import Module1 from './modules/module1.store';
import Module2 from './modules/module2.store';
import Module3 from './modules/module2.store';

Vue.use(Vuex);
const debug = process.env.NODE_ENV !== 'production';
export default new Vuex.Store({
  modules: {
    Module1,
    Module2,
    Module3,
  },
  strict: debug, // if a state is mutated outside of mutation handlers, an error will be thrown.
  plugins: debug? [ createLogger() ] : [],  // set logger only for development
})
```

</div>
</div>

<!--
- Note that, each module is named as ModuleName.store.js this will help us to auto-import these modules and we'll discuss it in the next section.
-->
