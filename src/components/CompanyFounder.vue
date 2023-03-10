<template>
  <div>
    <p>Please enter the founder's unique ID to get started.</p>
    <label>
      Founder ID:
      <input type="text" v-model.lazy="founderId" placeholder="Any characters will do..." />
    </label>
    <!-- Pass founderId to FounderDataFetcher -->
    <FounderDataFetcher v-if="founderId" :founder-id="founderId" />
  </div>
</template>

<script>
import FounderDataFetcher from './FounderDataFetcher.vue';

export default {
  data() {
    return {
      founderId: '',
    };
  },
  components: {
    FounderDataFetcher,
  },
};
</script>
