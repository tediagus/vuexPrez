
# La mutation
<div class="grid grid-cols-2 gap-4">
<div>

* Définition
<p class="text-sm">
C'est une fonction qui nous autorise à modifier la valeur d'une propriété du store
</p>

* Implémentation d'une mutation
```ts{5,6,7,8,10,11,12}
const store = new Vuex.Store({
    state: {
        count: 1 ; // état à l'initialisation
    },
    mutations:{
        increment(state) {  
            // changement de l'etat (muter)
            state.count++
        },
        // avec un argument additionnel :
        increment(state, payload) { 
            state.count += payload.increment
        },
    }
})
```
</div>

<div>

* Utilisation

```ts{2,4}
// pour appeler la mutation 
store.commit('increment')
// avec un argument additionnel :
store.commit('increment', 2)
```

* Bonne pratique pour l'écriture des mutations (ce n'est pas une obligation)

Utiliser des constantes pour les types de mutation peut apporter de la clarté dans la lecture du code (c'est dans les standards)



```ts
 const MA_MUTION = MA_MUTATION
...
 mutations: {
     [MA_MUTATION] ( state ) { ...}
 } 
 ...
 ````
  
* Petit rappel 
la mutation est synchrone
</div>

</div>

<!--
Il est possible de passe tout type de valeur dans l'argument additionnels
object, string, boolean etc...

il est conseillé de passer un object car cela rend la mutation plus descriptives


On peut également appliquer un linter
-->
