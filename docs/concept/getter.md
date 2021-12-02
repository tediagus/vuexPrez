---
layout: two-cols
---
## Le getter (accesseurs)

C'est une méthode qui permet d'effectuer des actions ou opération sur un state dans le store.

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
 