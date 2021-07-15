<template>
  <aside>
    <div v-for="item in items" :key="item.title">
      {{ item.title }}
      {{ item.description }}
    </div>
  </aside>
</template>

<script>
import Vue from 'vue'
import { markRaw } from '@nuxtjs/composition-api'

export default Vue.extend({
  setup () {
    const items = markRaw([
      {
        title: 'title',
        description: 'djfkkfk description description'
      }
    ])
    return {
      items
    }
  }
})
</script>

<style scoped>
aside {
  border: 1px solid red;
}
</style>
