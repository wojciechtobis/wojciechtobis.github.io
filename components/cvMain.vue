<template>
  <main>
    <cv-section>
      <template #title>
        Profile
      </template>
      <cv-section-item>
        {{ cvData.profile }}
      </cv-section-item>
    </cv-section>
  </main>
</template>

<script lang="ts">
import { markRaw } from '@nuxtjs/composition-api'
import Vue from 'vue'

import CvSection from './cvSection.vue'
import CvSectionItem from './cvSectionItem.vue'

export default Vue.extend({
  name: 'CvMain',

  components: {
    CvSection,
    CvSectionItem
  },

  setup () {
    const cvData = markRaw({
      profile: 'I am a passionate front-end developer and web designer with a strong desire for personal development. My strengths include ability to work under pressure, organization skills and analytical thinking. I am known as a person with enthusiastic approach to new ideas and ability to solve problems.',
      experience: [
        {
          time: '09/2019 - 01/2020',
          position: 'Front-end Developer',
          company: 'NetEnt',
          description: 'Developing, maintaining and supporting internal game frameworks (JSON form editor with React/TypeScript and Material-UI, sound library based on events in TypeScript) in international Agile environment.'
        }
      ],
      education: [
        {
          field: 'Technical Physics, second circle of studies',
          time: '2015 - 2018 (completion of studies without defending the degree)',
          uni: 'Faculty of Physics and Applied Computer Science \n AGH University of Science and Technology'
        }
      ]
    })

    return {
      cvData
    }
  }
})
</script>
