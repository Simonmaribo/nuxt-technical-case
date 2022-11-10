<template>
  <div class="container">
    <h1>Welcome!</h1>
    <h2>See open campaigns below</h2>
    <div class="campaign">
      <img src="https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/K3OkZOAFtkVplTVUkwn2x">
      <h3>Campaign Title</h3>
      <h4>Campaign Description</h4>
    </div>
    <h3>
      Dummy campaign data
    </h3>
    <p>
      {{ campaigns }}
    </p>
  </div>
</template>

<style lang="scss" scoped>
.campaign {
  padding: 20px;
  border: solid 1px black;
  margin: 20px;
  display: inline-block;
  img {
    width: 350px;
  }
}
.container {
  padding: 50px;
}
</style>
<script>
//use the campaigns from the data variable campaigns

export default {
  name: 'IndexPage',
  async asyncData({ $axios }) {
    return {
      campaigns: await $axios.$get("/"),
      loading: true,
      error: null
    }
  }
}
</script>
