


# Mise en place d'un store

<div class="grid grid-cols-2 gap-4">

<div>

#### Création d'un script contenant où on l'on crée une instance Vuex

```ts
import Vuex from 'vuex'

const state = {}

const mutations ={}

const actions =  {}

const getters = {}

export default new Vuex.Store({
    state,
    getter,
    actions,
    mutations
})

```
</div>
<div>

#### Instanciation du store dans l'application

##### Dans le script app.vue 

```ts{2,6}
    import Vue from 'vue'
    import store from './store'

    new Vue({
    el: '#app',
    store,
    ...
    })
```

</div>

</div>