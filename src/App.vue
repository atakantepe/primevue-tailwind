<script setup>

</script>

<template>
  <div class="main">
    <div class="card">
      <a href="https://primevue.org/" target="_blank">
        <img src="./assets/primevue-icon.svg" class="logo vue" alt="PrimeVue logo" />
      </a>
      <h1>Tailwind CSS Based UI Component Library for Vue.js</h1>
      <p>PrimeVue team is working on a brand new customizable preset implemented with Tailwind CSS.</p>
      <div class="pbar">
          <div class="pbar-value"></div>
      </div>
      <span>Coming Soon</span>
    </div>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
