<template>
  <div>
    <div v-if="isLoading">Loading...</div>
    <div v-else>
      <img class="avatar" :src="avatarURL" alt="Founder's avatar" width="150" />
      <h2 class="founder-name">{{ founderTitle }} {{ founderName }}</h2>
      <div class="cont-result">
        <p>Age:</p>
        <p>{{ founderAge }}</p>
        <p>Nationality:</p>
        <p>{{ founderNat }}</p>
        <p>Email:</p>
        <p>{{ founderEmail }}</p>
        <p>Company founded:</p>
        <p class="company-name">{{ companyName }}</p>
        <p>Company website:</p>
        <p><a :href="companyWebsite" rel="noopener noreferrer" target="_blank">{{ companyWebsite }}</a></p>
        <br><br><br>
      </div>
    </div>
  </div>
</template>

<style>
@import "./styles.css";
</style>

<script>
// Transform characters into unicode as seed of fakerapi only works with numbers:
function transformFounderId(founderId) {
  const charCodes = founderId.split('').map((char) => char.charCodeAt(0));
  const transformedId = charCodes.join('');
  return transformedId;
}

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
      founderTitle: '',
      founderName: '',
      founderEmail: '',
      founderAge: '',
      founderNat: '',
      companyName: '',
      companyWebsite: '',
      avatarURL: '',
    };
  },
  async mounted() {
    try {
      const transformedId = transformFounderId(this.founderId);

      // Fetch founder data
      const founderResponse = await this.$http.get(
        `https://randomuser.me/api/?seed=${this.founderId}`,
      );

      const founder = founderResponse.data.results[0];
      this.founderTitle = `${founder.name.title}`;
      this.founderName = `${founder.name.first} ${founder.name.last}`;
      this.founderEmail = `${founder.email}`;
      this.founderAge = `${founder.dob.age}`;
      this.founderNat = `${founder.nat}`;

      // Fetch company data
      const companyResponse = await this.$http.get(
        `https://fakerapi.it/api/v1/companies?_seed=${transformedId}`,
      );

      const company = companyResponse.data.data[0];
      this.companyName = `${company.name}`;
      this.companyWebsite = `${company.website}`;

      // Fetch avatar
      const avatarResponse = await this.$http.get(
        `https://robohash.org/${this.founderId}`,
      );

      this.avatarURL = avatarResponse.request.responseURL;
      this.isLoading = false;
    } catch (error) {
      this.isLoading = false;
    }
  },
};
</script>
