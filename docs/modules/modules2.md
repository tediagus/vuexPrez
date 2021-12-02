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