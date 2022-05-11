<template>
  <component :is="tag" class="cv-section-item" :class="{'cv-section-item--no-header': !withHeader}">
    <header v-if="withHeader" class="cv-section-item__header">
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
  break-inside: avoid-page;

  + .cv-section-item {
    margin-top: calc(var(--unit) * 8);
  }

  &--no-header {
    p {
      font-size: calc(var(--paragraph-size) * 1);
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

  &__header {
    margin-bottom: calc(var(--unit) * 2);
  }

  &__subtitle {
    color: var(--primary);
  }
}
</style>
