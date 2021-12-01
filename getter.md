---
layout: two-cols
---
## Le getter (accesseurs)

C'est une methode qui permet d'effectuer des actions ou opération sur un state dans le store

exmple

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
 

 BAD

 Ne pas juste retourner le state
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
 