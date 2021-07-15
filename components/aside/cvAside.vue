<template>
  <aside class="cv-aside">
    <h2 class="cv-aside__hidden-h2">
      More info
    </h2>
    <cv-section v-for="item in items" :key="item.title" small>
      <template #title>
        <span v-html="item.title" />
      </template>
      <p v-html="item.description" />
    </cv-section>
    <blockquote class="cv-aside__agreement">
      {{ agreement }}
    </blockquote>
  </aside>
</template>

<script lang="ts">
import Vue from 'vue'
import { markRaw } from '@nuxtjs/composition-api'
import CvSection from '../cvSection.vue'

export default Vue.extend({
  components: {
    CvSection
  },
  setup () {
    const items = markRaw([
      {
        title: 'Details',
        description: 'Kraków <br/>+48 669 594 719 <br/><a href="https://www.linkedin.com/in/ktobis/" target="_blank">linkedin.com/in/ktobis</a><br/><a href="https://github.com/katarzynatobis" target="_blank">github.com/katarzynatobis</a><a href="https://www.behance.net/katawes" target="_blank"><br/>behance.net/katawes</a>'
      },
      {
        title: 'Languages',
        description: 'Polish (native)<br/>English (B2)'
      },
      {
        title: 'Skills &&nbsp;Tools',
        description: 'JavaScript, TypeScript, Vue, React, HTML&nbsp;5, CSS&nbsp;3, PostCSS, MobX, Git, Cypress, Adobe&nbsp;CC'
      },
      {
        title: 'Honors &&nbsp;Awards',
        description: '<p>HackYeah hackathon, X-&zwj;SOCIAL category &mdash;&nbsp;finalist (2017)</p><p>the European BEST Engineering Competition &mdash;&nbsp;4th place in Poland (2013)</p>'
      },
      {
        title: 'Passions',
        description: 'Dog training &&nbsp;behaviour<br/>Front-end development<br/>Fantasy &&nbsp;popular&nbsp;science literature<br/>Traveling &&nbsp;hitchhiking<br/>Scouting'
      },
      {
        title: 'Volunteering',
        description: '<p>React &&nbsp;TypeScript Mentor &mdash;&nbsp;DevMeetings</p><p>Scout guide &mdash;&nbsp;The&nbsp;Polish Scouting and Guiding Association (ZHP)</p>'
      }
    ])

    const agreement = 'I hereby agree to the processing of personal data included in my application for the needs necessary to carry out the recruitment process in accordance with art. 6 par. 1 lit. a Regulation (EU) 2016/679 of the European Parliament and of the Council of 27 April 2016 on the protection of individuals with regard to the processing of personal data and on the free movement of such data and repealing Directive 95/46/EC (General Data Protection Regulation). I also consent to processing of my personal data for the purposes of any future recruitment processes.'
    return {
      items,
      agreement
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
