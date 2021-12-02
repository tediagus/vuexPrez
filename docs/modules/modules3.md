
#### Réinitialiser les states

<div class="grid grid-cols-2 gap-4">
<div>

**Individuellement**
```js 
const initialState = () => ({
  variable1: value,
  variable2: value,
  variable3: value
});

const state = initialState();

// Mutations
const mutations = {
  RESET(state) {
    Object.assign(state, initialState())
  },
}

// Actions
const actions = {
  reset({ commit }) {
    commit('RESET')
  },
}
```

</div>
<div>

**Globalement**
```js
import Vue from 'vue'
import Vuex from 'vuex'
import createLogger from 'vuex/dist/logger'
import modules from './modules';

Vue.use(Vuex);
const debug = process.env.NODE_ENV !== 'production'

export default new Vuex.Store({
  modules,
  actions: {
    reset({commit}) {
      // resets state of all the modules
      Object.keys(modules).forEach(moduleName => {
        commit(`${moduleName}/RESET`)
      })
    }
  },
  strict: debug,
  plugins: debug ? [createLogger()] : [] // set logger only for development
})
```

```js
this.$store.dispatch('reset');
```

</div>
</div>

