<template>
  <main>
    <section />
  </main>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  name: 'CvMain',

  setup () {
    return {
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
    }
  }
})
</script>
