<template>
  <div>
    <div class="cont-fetch">
      <p id="instruction">Please enter the founder's unique ID to get started.</p>
      <label class="label">
        Founder ID:
        <input class="input" type="text" v-model.lazy="founderId" placeholder="Any characters will do..." />
      </label>
      <FounderProfile v-if="founderId" :founder-id="founderId" :key="founderId" />
    </div>
  </div>
</template>

<style>
  @import "./styles.css";
</style>

<script>
import FounderProfile from './FounderProfile.vue';

export default {
  data() {
    return {
      founderId: '',
    };
  },
  components: {
    FounderProfile,
  },
};
</script>
