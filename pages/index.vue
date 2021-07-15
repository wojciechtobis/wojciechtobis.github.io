<template>
  <cv :data="data" />
</template>

<script lang="ts">
import Vue from 'vue'
import { markRaw } from '@nuxtjs/composition-api'
import en from '~/assets/data/en.js'
import Cv from '~/components/cv.vue'

export default Vue.extend({
  components: {
    Cv
  },
  setup () {
    const data = markRaw(en)
    return {
      data
    }
  }
}
)
</script>
