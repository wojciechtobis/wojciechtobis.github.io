<template>
  <div class="layout">
    <button class="print-button" @click="printCv">
      Print me!
    </button>
    <Nuxt />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  setup () {
    function printCv () {
      window.print()
    }

    return { printCv }
  }
})
</script>

<style lang="postcss" scoped>
.layout {
  --cv-width: calc(var(--unit) * 250);

  width: var(--cv-width);
  position: relative;
  min-width: var(--cv-width);
  margin: calc(var(--unit) * 25) auto;
  background: white;
  box-shadow: var(--primary-dark) 4px 4px 8px 0;

  @media screen and (max-width: env(--tablet)) {
    --cv-width: 80vw;
  }

  @media screen and (max-width: env(--mobile)) {
    --cv-width: 85vw;

    margin-top: calc(var(--unit) * 15);
  }

  @media print {
    --cv-width: 210mm;

    margin: 0;
    box-shadow: none;
  }
}

.print-button {
  position: absolute;
  top: -calc(var(--unit) * 8);
  left: -calc(var(--unit) * 3);
  border: 1px solid var(--primary);
  padding: calc(var(--unit) * 2) calc(var(--unit) * 4);
  font-family: var(--sans-serif);
  font-size: var(--paragraph-size);
  box-shadow: var(--primary-dark) 2px 2px 4px 0;
  cursor: pointer;
  background-color: var(--primary);
  color: white;
  transition: background-color 200ms ease-in;

  &:hover {
    background-color: var(--primary-dark);
  }

  @media print {
    display: none;
  }
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
