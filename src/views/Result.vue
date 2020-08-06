<template>
  <b-container class="mt-3">
    <h3>好きなTwitterアカウントのツイートをワードクラウドにします</h3>
    <b-container>
      <p>こんなツイートをしてるみたい</p>
      <div class="mt-3">Debug: {{ username }}</div>
      <img src="../assets/testimg/tomneko12151303_TP_V4.jpg" />
    </b-container>
  </b-container>
</template>

<script>
export default {
  props: {
    username: String,
  },
  data() {
    return {
      loading: false,
      img: "",
    };
  },
  created: {
    sendDataToAPI() {
      this.loading = true;
    },
  },
  methods: {},
};
</script>