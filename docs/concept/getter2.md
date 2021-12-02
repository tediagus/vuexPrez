
# Point d'attention 
* A éviter : 
<div class="bg-orange-400">
 Utiliser un accesseur pour renvoyer le state
</div>

```ts
     doneTodos: state => return state.todos
```
* Conseillé
<div class="bg-green-400">
 Utiliser l'accesseur pour renvoyer une valeur calculée
</div>

```ts
getters: {
    doneTodos: state =>  state.todos.filter(todo => todo.dones)
}
    ```


