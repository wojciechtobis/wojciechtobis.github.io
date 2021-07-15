<template>
  <div class="layout">
    <Nuxt />
  </div>
</template>

<style>
.layout {
  --cv-width: calc(var(--unit) * 250);

  width: var(--cv-width);
  min-width: var(--cv-width);
  margin: calc(var(--unit) * 25) auto;
  background: white;
  box-shadow: var(--primary-dark) 4px 4px 8px 0;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
