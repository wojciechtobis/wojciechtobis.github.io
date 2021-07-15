<template>
  <section class="cv-section" :class="{'cv-section--small': small}">
    <header>
      <component :is="headingTag">
        <slot name="title" />
      </component>
    </header>
    <slot />
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import { computed } from '@nuxtjs/composition-api'

export default Vue.extend({
  props: {
    small: {
      type: Boolean
    }
  },
  setup ({ small }) {
    const headingTag = computed(() => small ? 'h3' : 'h2')
    return {
      headingTag
    }
  }
})
</script>

<style lang="postcss" scoped>
.cv-section {
  margin: calc(var(--unit) * 12) 0;

  h2 {
    margin-bottom: calc(var(--unit) * 8);
  }

  &--small {
    font-size: calc(var(--paragraph-size) * 0.8);

    &:first-of-type {
      margin-top: 0;
    }

    h3 {
      font-family: var(--serif);
      margin-bottom: calc(var(--unit) * 4);
      color: var(--primary);

      &::first-letter {
        text-transform: capitalize;
      }
    }
  }
}
</style>
