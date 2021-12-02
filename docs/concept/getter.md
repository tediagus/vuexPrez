
# Le getter (accesseur)
<div class="grid grid-cols-2 gap-4">
<div>

### <u>Définitons</u>

C'est une méthode qui permet d'effectuer des actions ou opérations sur un attribut du le store.

```ts
    state: {
    todos: [
    { id: 1, text: '...', done: true },
    { id: 2, text: '...', done: false }
    ]
},
    getters: {
    doneTodos: state => {
    return state.todos.filter(todo => todo.done)
    }
}
```

Le résultat de l'accesseur est mis en cache. Il ne sera ré-évaluer que si une dependance change.

on peut accèder a la propriété  de la manière suivant:

```ts
store.getters.doneTodos 
// -> [{ id: 1, text: '...', done: true }]
```
</div>
<div>
Dans un composant il sera instancier dans la proriété computed

```ts

 export default {
 ...
computed: {
  doneTodosCount () {
    return this.$store.getters.doneTodosCount
  }

//Le plus fréquent 
//Rajouter les accesseurs dans `computed`
// avec l'opérateur de décomposition */
...mapGetters([
      'doneTodosCount',
      'anotherGetter',
    ])
  }
}
```
</div>
</div>