<template>
  <div v-if="isLoading">Loading...</div>
  <div v-else>
    <img :src="avatarUrl" alt="Founder's avatar">
    <h2>{{ name }}</h2>
    <p>{{ email }}</p>
    <p>{{ company }}</p>
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
      name: '',
      email: '',
      company: '',
      avatarUrl: '',
    };
  },
  created() {
    Promise.all([
      this.fetchDemographicData(),
      this.fetchCompany(),
      this.fetchAvatar(),
    ]).then(([demographicData, companyData, avatarUrl]) => {
      this.name = `${demographicData.name.title} ${demographicData.name.first} ${demographicData.name.last}`;
      this.email = demographicData.email;
      this.company = companyData.name;
      this.avatarUrl = avatarUrl;
      this.isLoading = false;
    });
  },
  methods: {
    async fetchDemographicData() {
      const response = await fetch('https://randomuser.me/api/');
      const data = await response.json();
      return data.results[0];
    },
    async fetchCompany() {
      const response = await fetch('https://fakerapi.it/api/v1/companies');
      const data = await response.json();
      return data.data[0];
    },
    async fetchAvatar() {
      const email = encodeURIComponent(`${this.name}@example.com`);
      const url = `https://robohash.org/${email}?size=150x150`;
      return Promise.resolve(url);
    },
  },
};
</script>
