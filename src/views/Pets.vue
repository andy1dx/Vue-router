<template>
  <div>
    <h1>{{ animal.name }} ({{ $route.params.species }})</h1>
    <p>AGE : {{ animal.age }}</p>
    <p>BREED : {{ animal.breed }}</p>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    console.log(animal)
    this.animal = animal
  }
}
</script>
