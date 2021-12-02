---
layout: two-cols
---

## Le state 

<br />

### Définition:

On appel "state":

l'état d'un objet au niveau applicatif. 

C'est à dire une propriété suceptible d'être employée dans divers composant de notre application.
et dont la valeur evolura tout au long de l'application.

Si cet état est amené à changer on dit qu'elle subit une "mutation"

::right::

#### Comment récuperer l'état d'un store dans un composant

```ts
    this.$store.state.nomDeMonAttribut
```

l'une des plus utilisé et la syntaxe destructurer
```ts
import { mapState } from 'vuex' 

    // avec la fonction mapState 
    export default{
       // ...
        computed: {
            ...mapState({nomDeMonAttibut})
        }
       
    }
    ...
```