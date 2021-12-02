
# L'action

<div class="grid grid-cols-2 gap-4">
<div>

* <u>Définition : </u>

C'est une fonction qui permet de modifier l'état d'une propriété à la différence de la mutation, l'action peut être
asynchrone

* <u>Cas d'usage :</u>

<div clalss="list-item">

Toutes  mutations devraient avoir une action associée. 
<br />
  
Une action devrait être utilisée pour :
 
  Récupérer de la donnée par un appel d'API <br>
  Effectuer des mutations ou dispatch d'autres actions
  
 S'il y a trop de logic il faut penser au `Plugin`
 </div>
</div>
<div>

* <u>Implémentation</u>

```ts
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  },
  actions: {
    increment (context) {
      context.commit('increment')
    }
  }
})
```

```js
context = { // context can also be destructuring like so: "increment({ commit }) {...}", see all the properties below
  state,      // same as store.state, or local state if in modules
  rootState,  // same as store.state, only in modules
  commit,     // same as store.commit
  dispatch,   // same as store.dispatch
  getters,    // same as store.getters, or local getters if in modules
  rootGetters // same as store.getters, only in modules
}
```


</div>
</div>

