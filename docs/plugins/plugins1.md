---
layout: full
---

# Les plugins

Un plugin Vuex est simplement une fonction qui reçoit le store comme seul argument. <br>
Fonction qui est déclenchée/appelée lorsqu'un certain type de mutation ou d'action est appelé dans Vuex. <br>
Peut aussi être utilisé globalement (pour toutes les mutations ou actions).

<div class="grid grid-cols-2 gap-4">
<div>

**Construction d'un plugin**

Mutations
```js
export default (store) => {
  store.subscribe((mutation) => {
    if (mutation.type === "STORE_ERRORS") {
      console.log(mutation.type, mutation.payload)
    }
  })
}
```

Actions
```js 
store.subscribeAction((action) => {
  if (action.type === "getTodos") {
    console.log(action.type, action.payload)
  }
})
```

</div>
<div>

**createLogger : plugin de logs intégré**
```js
import createLogger from 'vuex/dist/logger'

const debug = process.env.NODE_ENV !== 'production'

const store = new Vuex.Store({
  plugins: debug ? [createLogger()] : []
})
```

</div>
</div>

<!--
Vuex plugins are among the most advanced and useful concepts in Vuex. They have a wide variety of use cases, from data persistence, to Slack Notifier, to enhacing Vuex itself.


Each time you commit a mutation, it should do only ONE thing: Update the value of the state.

Each time you dispatch an action, it should do one or more of the following:
(i) Fetch data from an API.
(ii) Commit a mutation.
(iii) Dispatch an action.

Each time you find yourself executing logic that falls outside of these core responsibilities, you should consider extracting that logic inside a Vuex plugin.
-->
