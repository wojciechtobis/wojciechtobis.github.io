<template>
  <div class="cv">
    <div>
      <cv-header />
      <cv-main :data="data.main" />
    </div>
    <cv-aside :data="data.aside" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import CvHeader from './cvHeader.vue'
import CvMain from './main/cvMain.vue'
import CvAside from './aside/cvAside.vue'

export default Vue.extend({
  components: {
    CvHeader,
    CvMain,
    CvAside
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
.cv {
  display: grid;
  grid-template-columns: 5fr 2fr;

  & > * {
    padding: calc(var(--unit) * 25);
    padding-top: calc(var(--unit) * 35);

    @media print {
      padding: calc(var(--unit) * 10);
      padding-top: calc(var(--unit) * 20);
    }

    &:first-child {
      padding-right: calc(var(--unit) * 10);
    }
  }
}
</style>
