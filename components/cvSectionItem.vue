<template>
  <component :is="tag" class="cv-section-item" :class="{'cv-section-item--no-header': !withHeader}">
    <header v-if="withHeader">
      <h3 v-if="$slots.title" class="cv-section-item__title">
        <slot name="title" />
      </h3>
      <div v-if="$slots.subtitle" role="doc-subtitle" class="cv-section-item__subtitle">
        <slot name="subtitle" />
      </div>
    </header>
    <p>
      <slot />
    </p>
  </component>
</template>

<script lang="ts">
import { computed } from '@nuxtjs/composition-api'
import Vue from 'vue'

export default Vue.extend({
  props: {
    tag: {
      type: String,
      default: 'article'
    }
  },
  setup (_props, { slots }) {
    const withHeader = computed(() => slots.title && slots.subtitle)

    return {
      withHeader
    }
  }
})
</script>

<style lang="postcss" scoped>
.cv-section-item {
  position: relative;
  padding-left: calc(var(--unit) * 8);

  &--no-header {
    p {
      font-size: calc(var(--paragraph-size) * 1.25);
    }
  }

  &::before {
    content: '';
    position: absolute;
    width: calc(var(--unit) / 2);
    background: var(--primary);
    bottom: 5px;
    top: 7px;
    left: 0;
  }

  &__title {
    font-family: var(--serif);
  }

  &__subtitle {
    font-family: var(--sans-serif);
    color: var(--primary);
  }
}
</style>
