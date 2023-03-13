<template>
  <div class="app-background">
    <img alt="Vue logo" src="./assets/briefcase.svg" />
    <h1 class="app-h1">Information about company founders</h1>
  </div>
  <CompanyFounder />
</template>

<script>
import CompanyFounder from './components/CompanyFounder.vue';

export default {
  name: 'App',
  components: {
    CompanyFounder,
  },
};
</script>

<style>
@import "./components/styles.css";
</style>
