<div>
<div>

* <u>Utilisation d'un action</u>

```ts

store.dispatch('increment')

//  dans un composant
this.$store.dispatch 
// avec la fonction utilisataire `mapActions` dans la `methods`

import { mapActions } from 'vuex'

//...
  methods: {
    ...mapActions([
      'increment'
    ]),

// on peut ensuite appeler l'action dans une methode du composant 
    add: (){
        this.increment()
    }
  }
```

</div>

</div>