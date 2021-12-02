---
layout: full
---

# Gestion des formulaires

Il n'est pas possible d’utiliser v-model "normalement" avec Vuex, il faut créer une computed property comprenant get() et set()

<div class="grid grid-cols-2 gap-4">
<div>

**Template**

```js 
<input v-model="message">
```

</div>
<div>

**Script**
```js
computed: {
  message: {
    get () {
      return this.$store.state.obj.message
    },
    set (value) {
      this.$store.commit('updateMessage', value)
    }
  }
}
```

</div>
</div>
