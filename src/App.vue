<template>
  <img alt="Vue logo" src="./assets/briefcase.svg" />
  <h1>Information about company founders</h1>
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img {
  height: 150px;
}
</style>
