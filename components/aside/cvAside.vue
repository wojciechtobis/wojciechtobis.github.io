<template>
  <aside class="cv-aside">
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

<style lang="postcss" scoped>
.cv-aside {
  border-left: 1px solid var(--primary);
  padding: calc(var(--unit) * 25);
  padding-left: calc(var(--unit) * 15);
}
</style>
