
# Le Getter (Accesseur)
<div class="grid grid-cols-2 gap-4">
<div>

* <u>Définition</u>
<p class="text-sm">
C'est une méthode qui permet d'effectuer des actions ou opérations sur un attribut du store
</p>

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

<p class="text-sm">
Le résultat du getter est mis en cache. Il sera ré-évaluer si une dépendance du store vient à changer.
</p>

</div>
<div>


* Accès à la propriété

```ts
store.getters.doneTodos 
// -> [{ id: 1, text: '...', done: true }]
```

* Utilisation du getter dans un composant

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
...mapGetters({
      doneTodosCount,
      anotherGetter,
    })
}
```
</div>
</div>