<template>
  <div class="container">
    <h1>Welcome!</h1>
    <h2>See open campaigns below</h2>
    <div class="campaign">
      <img src="https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/K3OkZOAFtkVplTVUkwn2x">
      <h3>Campaign Title</h3>
      <h4>Campaign Description</h4>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.campaign {
  padding: 20px;
  border: solid 1px black;
  margin: 20px;
  display: inline-block;
  img {
    width: 150px;
  }
}
.container {
  padding: 50px;
}
</style>
<script>
//use the campaigns from the data variable campaigns
const campaigns = [{
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/CJhc8MG_fl_5Df_nJHGso",
  description: "Vi søger ambassadører der kan skabe opmærksomhed omkrig Foto Factory.",
  title: "Copy of fesfes",
  uid: "qUm0vueM7"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/TORCSDfv2dqHWkzQxYSFN",
  description: `Hello! 

We're currently looking for tiktokkers to be in our videos for Pico's own TikTok account. If interested please join the campaign, and we will then message you when we spot a trend we think you'd be a good fit for. 

One hour of your time will be rewarded with a gift card for 2 x Pico Trio to enjoy with a friend any time you want.  `,
  title: "fesfes",
  uid: "Sp5hr9zuc"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/K3OkZOAFtkVplTVUkwn2x",
  description: "You can choose 2 clothes from our new winter collection",
  title: "Test2",
  uid: "C-7zfkTsV"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/eEsUrsA4NW40xSji-DsUo",
  description: `We are excited to kick off our ZENZ TikTok campaign. We would love for you to be one of our first influencers to promote ZENZ Organic on TikTok!

In this campaign we want you to share with your followers that ZENZ Organic is more than just a quality beauty and haircare brand, but our products are also made from natural and organic ingredients. ZENZ Organic are developed by hairdressers, and we prioritize health and sustainability together with a high quality. 

The campaign period is from 15st of July - 15st of August. When you have joined the campaign you will receive a voucher code so you can order your favorite products from our website.  

For this campaign you need to use the hashtags: #ZENZOrganic and #ZENZOrganicProducts #ZenzNetherlands #ZenzAmbassador and tag @ZENZOrganic`,
  title: "ZENZ TikTok Kickoff Campaign NLh",
  uid: "IUVRvbhM-r342awfdwafse"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/0EyFa2VzF2FMER4slWZuk",
  description: "Products from Frederik Bagger (worth up to 3000NOK)",
  title: "Frederik Bagger Norwegian Launch",
  uid: "IUVRvbhdawM-r342awfdwafse"
},{
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/CJhc8MG_fl_5Df_nJHGso",
  description: "Vi søger ambassadører der kan skabe opmærksomhed omkrig Foto Factory.",
  title: "Copy of fesfes",
  uid: "qUm0vueM7"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/TORCSDfv2dqHWkzQxYSFN",
  description: `Hello! 

We're currently looking for tiktokkers to be in our videos for Pico's own TikTok account. If interested please join the campaign, and we will then message you when we spot a trend we think you'd be a good fit for. 

One hour of your time will be rewarded with a gift card for 2 x Pico Trio to enjoy with a friend any time you want.  `,
  title: "fesfes",
  uid: "Sp5hr9zuc"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/K3OkZOAFtkVplTVUkwn2x",
  description: "You can choose 2 clothes from our new winter collection",
  title: "Test2",
  uid: "C-7zfkTsV"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/eEsUrsA4NW40xSji-DsUo",
  description: `We are excited to kick off our ZENZ TikTok campaign. We would love for you to be one of our first influencers to promote ZENZ Organic on TikTok!

In this campaign we want you to share with your followers that ZENZ Organic is more than just a quality beauty and haircare brand, but our products are also made from natural and organic ingredients. ZENZ Organic are developed by hairdressers, and we prioritize health and sustainability together with a high quality. 

The campaign period is from 15st of July - 15st of August. When you have joined the campaign you will receive a voucher code so you can order your favorite products from our website.  

For this campaign you need to use the hashtags: #ZENZOrganic and #ZENZOrganicProducts #ZenzNetherlands #ZenzAmbassador and tag @ZENZOrganic`,
  title: "ZENZ TikTok Kickoff Campaign NLh",
  uid: "IUVRvbhM-r342awfdwafse"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/0EyFa2VzF2FMER4slWZuk",
  description: "Products from Frederik Bagger (worth up to 3000NOK)",
  title: "Frederik Bagger Norwegian Launch",
  uid: "IUVRvbhdawM-r342awfdwafse"
}];
export default {
  name: 'IndexPage',
  data() {
    return {
      campaigns: campaigns,
      loading: true,
      error: null
    }
  }
}
</script>
