

Ce qu'il n'est pas conseillé de faire 

 Utiliser un getter pour renvoyer le state

```ts
     doneTodos: state => {
        return state.todos
        }
```

 Good

 Renvoyer une valeur calculée

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