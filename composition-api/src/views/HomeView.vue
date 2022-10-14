<template>
  <div class="home">
    <input type="text" v-model="searched">
      <div v-for="name in finded" :key="name">
        {{name}}
      </div>
  </div>
</template>

<script>
import { computed, ref } from 'vue'

export default {
  name: 'HomeView',
  setup () {
    const names = ref(['tarik', 'hakan', 'sedat', 'zehra', 'hacer'])
    const searched = ref('')
    const finded = computed(() => {
      return names.value.filter((name) => name.includes(searched.value))
    })
    return {
      names,
      searched,
      finded
    }
  }
}
</script>
