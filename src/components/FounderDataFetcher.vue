<template>
  <div>
    <div v-if="isLoading">Loading...</div>
    <div v-else>
      <img :src="avatarURL" alt="Founder's avatar" width="150" />
      <h2>{{ founderName }}</h2>
      <h3>{{ companyName }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    founderId: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      isLoading: true,
      founderName: '',
      companyName: '',
      avatarURL: '',
    };
  },
  async mounted() {
    try {
      console.log(this.founderId);
      // Fetch founder data
      const founderResponse = await this.$http.get(
        `https://randomuser.me/api/?seed=${this.founderId}`,
      );
      const founder = founderResponse.data.results[0];
      this.founderName = `${founder.name.first} ${founder.name.last}`;
      // Fetch company data
      const companyResponse = await this.$http.get(
        `https://fakerapi.it/api/v1/companies?_seed=${this.founderId}`,
      );
      const company = companyResponse.data.data[0];
      this.companyName = company.name;
      // Fetch avatar
      const avatarResponse = await this.$http.get(
        `https://robohash.org/${this.founderId}`,
      );
      this.avatarURL = avatarResponse.request.responseURL;
      this.isLoading = false;
    } catch (error) {
      console.error(error);
      this.isLoading = false;
    }
  },
};
</script>
