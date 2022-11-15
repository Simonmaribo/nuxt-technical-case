<template>
  <div class="container">
    <DraggableContainer>
      <CampaignCard
        v-for="(campaign, index) in campaigns"
        :key="index"
        :campaign="campaign"
      />
    </DraggableContainer>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
  text-decoration: none !important;
  scroll-behavior: smooth;
}

body {
  background-color: #fefefe;
}

.container {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
<script>
//use the campaigns from the data variable campaigns

export default {
  name: "IndexPage",
  async asyncData({ $axios }) {
    return {
      campaigns: await $axios.$get("/"),
      loading: true,
      error: null,
    };
  },
};
</script>
