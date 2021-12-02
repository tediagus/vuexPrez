<div class="grid grid-cols-2 gap-4">
<div>

* <u>Utilisation d'un action</u>

```ts

store.dispatch('increment')

//  dans un composant
this.$store.dispatch 
// Avec la fonction utilisataire `mapActions` dans la `methods`

import { mapActions } from 'vuex'

//...
  methods: {
    ...mapActions([
      'increment'
    ]),

// on peut ensuite appeler l'action dans une methode du compsant 
    add: (){
        this.increment()
    }
  }
```

</div>

</div>