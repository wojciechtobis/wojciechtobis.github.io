<template>
  <div>
    <cv-header />
    <cv-main />
  </div>
</template>

<script>
import Vue from 'vue'
import CvHeader from './cvHeader.vue'
import CvMain from './cvMain.vue'

export default Vue.extend({
  components: {
    CvHeader,
    CvMain
  }
})
</script>
