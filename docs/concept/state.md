---
layout: full
---

# Le state  
<div class="grid grid-cols-2 gap-4">

<div>

<br />

### Définition:

<p class="text-base">
On appel `state`: un attribut du store. 

C'est une propriété avec une valeur initial qui sera utilisé dans divers composants de notre application,
et dont la valeur evolura tout au long de l'application.

Si cet état est amené à changer on dit qu'elle subit une "mutation"

</p>
  <div class="bg-blue-500">

###### Petit point d'attention 
<p class="text-sm">
Il est déconseilé de modifier un attribut du store directement en modifiant sa valeur.

```ts
    this.$store.state.age = 30 
```
Il est préférable d'utiliser une fonction qu'on appel `mutation` que nous verrons plus loin.
</p>
</div>
</div>

<div>

#### Comment récuperer l'état d'un store dans un composant


```ts
    this.$store.state.nomDeMonAttribut
```

l'une des plus utilisé et la syntaxe destructurer
```ts
import { mapState } from 'vuex' 
// Avec la fonction utilitaire mapState 
export default {
    // ...
    computed: {
        ...mapState({nomDeMonAttibut})
    }
}
```
<br />

</div>
</div>

