<template>
  <div id="app">
    <pvt-button ref="pvtbutton" v-bind:config="config"></pvt-button>
  </div>
</template>

<script>
const config = {
  flowType: "YOUR_FLOW_TYPE",
  credentials: {
    apiKey: "YOUR_API_KEY",
    clientSecret: "YOUR_CLIENT_SECRET",
    tenant: "YOUR_TENANT",
    banknu: "YOUR_BANKNU",
    env: "YOUR_ENV",
  },
  deskVerificationEnabled: true,
  currentUserInfo: {
    cifCode: "YOUR_CIFCODE",
  },
};
export default {
  name: "App",
  data() {
    return { config };
  },
  mounted: function () {
    const pvtButton = this.$refs.pvtbutton;
    pvtButton.addEventListener("loaded", () => pvtButton.initialize(config));
  },
};
</script>
