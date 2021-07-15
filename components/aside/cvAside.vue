<template>
  <aside class="cv-aside">
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
  padding: calc(var(--unit) * 25) calc(var(--unit) * 15) calc(var(--unit) * 25) calc(var(--unit) * 10);
  display: flex;
  flex-direction: column;

  &__hidden-h2 {
    height: 0;
    width: 0;
    overflow: hidden;
  }

  &__agreement {
    margin-top: auto;
    margin-bottom: 0;
    font-size: calc(var(--paragraph-size) * 0.5);
  }
}
</style>
