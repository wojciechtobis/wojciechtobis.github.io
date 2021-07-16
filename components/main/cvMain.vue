<template>
  <main>
    <cv-section>
      <template #title>
        Profile
      </template>
      <cv-main-item>
        {{ data.profile }}
      </cv-main-item>
    </cv-section>
    <cv-section>
      <template #title>
        {{ data.sections[0].title }}
      </template>
      <cv-main-item v-for="item in data.sections[0].items" :key="item.time">
        <template #title>
          {{ item.position }} @&nbsp;{{ item.company }}
        </template>
        <template #subtitle>
          {{ item.time }}
        </template>
        {{ item.description }}
      </cv-main-item>
    </cv-section>
    <cv-section>
      <template #title>
        {{ data.sections[1].title }}
      </template>
      <cv-main-item v-for="item in data.sections[1].items" :key="item.time">
        <template #title>
          {{ item.field }}
        </template>
        <template #subtitle>
          {{ item.time }}
        </template>
        <span v-html="item.uni" />
      </cv-main-item>
    </cv-section>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'

import CvSection from '../cvSection.vue'
import CvMainItem from './cvMainItem.vue'

export default Vue.extend({
  name: 'CvMain',

  components: {
    CvSection,
    CvMainItem
  },

  props: {
    data: {
      type: Object,
      required: true
    }
  }
})
</script>
