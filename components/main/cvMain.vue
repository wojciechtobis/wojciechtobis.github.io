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
    <cv-section>
      <template #title>
        {{ cvData.sections[0].title }}
      </template>
      <cv-section-item v-for="item in cvData.sections[0].items" :key="item.time">
        <template #title>
          {{ item.position }} @ {{ item.company }}
        </template>
        <template #subtitle>
          {{ item.time }}
        </template>
        {{ item.description }}
      </cv-section-item>
    </cv-section>
    <cv-section>
      <template #title>
        {{ cvData.sections[1].title }}
      </template>
      <cv-section-item v-for="item in cvData.sections[1].items" :key="item.time">
        <template #title>
          {{ item.field }}
        </template>
        <template #subtitle>
          {{ item.time }}
        </template>
        {{ item.uni }}
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
      sections: [
        {
          title: 'Experience',
          items: [
            {
              time: '02/2020 - present',
              position: 'Front-end Developer, Frontend Enginering Leader',
              company: 'NetEnt',
              description: 'Developing, maintaining and supporting Kinside products: childcare marketplace app (Vue 2, SCSS, Ruby on Rails), conducting code review, leading the front-end architecture, working in a distributed team (Poland, Canada, USA).'
            },
            {
              time: '09/2019 - 01/2020',
              position: 'Front-end Developer',
              company: 'NetEnt',
              description: 'Developing, maintaining and supporting internal game frameworks (JSON form editor with React/TypeScript and Material-UI, sound library based on events in TypeScript) in international Agile environment.'
            },
            {
              time: '07/2018 - 08/2019',
              position: 'Front-end Developer',
              company: 'Closer',
              description: 'Creating front-end for the Closer app, pixel-perfect implementation of designs, developing new and improving existing features, fixing bugs and refactoring using React with MobX, JavaScript/TypeScript and PostCSS.'
            },
            {
              time: '03/2016 - 06/2018',
              position: 'Web Designer',
              company: 'Idium Polska',
              description: 'Developing functional designs and webdesigns for clients (Norwegian market), developing original and innovative website templates, improving and testing the CMS.'
            },
            {
              time: '03/2014 - 06/2016',
              position: 'Lego Mindstorms Instructor',
              company: 'KRAUL sport, rekreacja, edukacja',
              description: 'Conducting courses for children and youth, assistance while building a robot, teaching programming (WeDo Software, Lego Mindstorms NXT and NXC) and building customer relationships.'
            }
          ]
        },
        {
          title: 'Education',
          items: [
            {
              field: 'Technical Physics, second circle of studies',
              time: '2015 - 2018 (completion of studies without defending the degree)',
              uni: 'Faculty of Physics and Applied Computer Science \n AGH University of Science and Technology'
            },
            {
              field: 'Technical Physics, first circle of studies',
              time: '2011 - 2015',
              uni: 'Faculty of Physics and Applied Computer Science \n AGH University of Science and Technology'
            }
          ]
        }
      ]
    })

    return {
      cvData
    }
  }
})
</script>
