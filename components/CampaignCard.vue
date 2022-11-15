<template>
    <div class="campaign-card">
        <div class="information">
            <h1>{{ campaignTitle }}</h1>
            <h2>{{ campaignDescription }}</h2>
        </div>
        <div class="campaign-cover" :style="`background-image: url(${campaignCover})`">
            <div class="details">
                <img class="campaign-logo" :src="campaignLogo" alt="Campaign Logo">
                <div>
                  <a :href="`/campaign/${campaignId}`" class="view-button">View</a>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

.campaign-card {
  margin: 10px;
}

.information {
  padding-bottom: 0.5rem;
}

.information h1 {
  margin: 0;
  font-size: 18px;
  color: #1c1917;
  font-weight: 500;
}
.information h2 {
  margin: 0;
  font-size: 14px;
  font-weight: 500;
  color: #79716B;
}

.campaign-cover {
  border-radius: 10px;
  width: 350px;
  height: 200px;
  background-size: cover;
  background-position: center;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  user-select: none;
}

.details {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.campaign-logo {
  width: 50px;
  height: 50px;
  border-radius: 10%;
}
.view-button {
  color: #fff;
  text-decoration: none !important;
  font-size: 12px;
  font-weight: 600;
  line-height: 16px;
  
  background-color:rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(12px);
  padding: 8px 14px;
  border-radius: 12px;

  cursor: pointer;
  cursor: -moz-pointer;
  cursor: -webkit-pointer;
  
  transition: all 0.1s ease-in-out;
}
.view-button:hover {
  background-color: rgba(255, 255, 255, 0.7);
}

</style>

<script>
export default {
  name: 'CampaignCard',
  props: {
    campaign: {
      type: Object,
      required: true
    }
  },
  computed: {
    campaignCover() {
      return this.campaign.coverURL || 'https://via.placeholder.com/300x120'
    },
    campaignLogo() {
      return this.campaign.logoURL || 'https://via.placeholder.com/50x50'
    },
    campaignTitle() {
      if(this.campaign.title?.length > 26)
        return this.campaign.title.substring(0, 26) + '...'
      return this.campaign.title || 'Untitled'
    },
    campaignDescription() {
      if(this.campaign.description?.length > 47)
        return this.campaign.description.substring(0, 47) + '...'
      return this.campaign.description || 'No description'
    },
    campaignId() {
      return this.campaign.uid || '0'
    }
  }
}
</script>