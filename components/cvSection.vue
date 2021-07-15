<template>
  <section class="cv-section">
    <header>
      <h2><slot name="title" /></h2>
    </header>
    <slot />
  </section>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({

})
</script>

<style lang="postcss" scoped>
.cv-section {
  margin: calc(var(--unit) * 12) 0;

  h2 {
    font-family: var(--serif);
    font-size: calc(var(--paragraph-size) * 1.75);
    margin-bottom: calc(var(--unit) * 8);
  }
}
</style>
