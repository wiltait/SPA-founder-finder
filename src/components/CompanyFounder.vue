<template>
  <div>
    <p>Please enter the founder's unique ID to get started.</p>
    <label>
      Founder ID:
      <input type="text" v-model="founderId" placeholder="Any characters will do..." />
    </label>
    <p v-if="founderId">
      You entered the founder ID '{{ founderId }}'… this seems like a good place to show their data…
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      founderId: '',
    };
  },
};
</script>
