<template>
  <div>
    <template v-if="!founderId">
      <p>Please enter the founder's unique ID to get started.</p>
      <label>
        Founder ID:
        <input type="text" v-model="founderId" placeholder="Any characters will do..." />
      </label>
    </template>
    <FounderDataFetcher v-else :founderId="founderId" />
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
