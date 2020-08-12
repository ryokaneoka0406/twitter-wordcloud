<template>
  <b-container class="mt-3">
    <h3>好きなTwitterアカウントのツイートをワードクラウドにします</h3>
    <b-container>
      <p>こんなツイートをしてるみたい</p>
      <div v-if="loading">読み込み中...</div>
      <b-img fluid :src="imgUrl" />
      <div v-if="imgUrl">
        <a :href="tweetLink" target="_blank">test</a>
      </div>
      <div class="mt-3">Debug: {{ username }}</div>
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
      imgUrl: "",
      tweetLink: "https://twitter.com/intent/tweet?text=",
    };
  },
  created() {
    this.sendDataToAPI();
  },
  methods: {
    sendDataToAPI() {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
        this.imgUrl = require("../assets/testimg/Figure_2.png");
        this.tweetLink = this.tweetLink + this.imgUrl;
      }, 1000);
    },
  },
};
</script>