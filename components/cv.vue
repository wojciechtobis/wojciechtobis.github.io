<template>
  <div class="cv">
    <div>
      <cv-header />
      <cv-main />
    </div>
    <cv-aside />
  </div>
</template>

<script>
import Vue from 'vue'
import CvHeader from './cvHeader.vue'
import CvMain from './cvMain.vue'
import CvAside from './cvAside.vue'

export default Vue.extend({
  components: {
    CvHeader,
    CvMain,
    CvAside
  }
})
</script>

<style lang="postcss" scoped>
.cv {
  --cv-width: calc(var(--unit) * 250);

  display: grid;
  grid-template-columns: 4fr 1fr;
  width: var(--cv-width);
  min-width: var(--cv-width);
  margin: calc(var(--unit) * 25) auto;
  background: white;

  & > *:first-child {
    padding: calc(var(--unit) * 25);
    padding-right: calc(var(--unit) * 15);
  }
}
</style>
