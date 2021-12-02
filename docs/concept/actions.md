
# L'action

<div class="grid grid-cols-2 gap-4">
<div>

* <u>Définitions: </u>

c'est une fonction qui permet de modifier l'état d'une propriété à la différence de la mutation, l'action peut être
asynchone.

* <u>cas d'usage:</u>

<div clalss="list-item">

Toutes  mutations devraient avoir une action associé. 
<br />
  
Une action devrait est etre utilisé pour :
 
  Reécupérer de la donnée par un appel d'API
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


</div>
</div>

