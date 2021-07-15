<template>
  <aside class="cv-aside cv-aside--spacing">
    <h2 class="cv-aside__hidden-h2">
      More info
    </h2>
    <cv-section v-for="item in data.sections" :key="item.title" small>
      <template #title>
        <span v-html="item.title" />
      </template>
      <p v-html="item.description" />
    </cv-section>
    <blockquote class="cv-aside__agreement">
      {{ data.agreement }}
    </blockquote>
  </aside>
</template>

<script lang="ts">
import Vue from 'vue'
import CvSection from '../cvSection.vue'

export default Vue.extend({
  components: {
    CvSection
  },
  props: {
    data: {
      type: Object,
      required: true
    }
  }
})
</script>

<style lang="postcss" scoped>
.cv-aside {
  border-left: 1px solid var(--primary);
  display: flex;
  flex-direction: column;

  &.cv-aside--spacing {
    padding-right: calc(var(--unit) * 15);
    padding-left: calc(var(--unit) * 10);

    @media print {
      padding-right: 0;
    }
  }

  &__hidden-h2 {
    height: 0;
    width: 0;
    overflow: hidden;
  }

  &__agreement {
    margin: 0;
    margin-top: auto;
    font-size: calc(var(--paragraph-size) * 0.5);
    break-inside: avoid-page;
  }
}
</style>
