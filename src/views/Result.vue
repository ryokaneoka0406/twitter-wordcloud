<template>
  <b-container class="mt-3">
    <h3>好きなTwitterアカウントのツイートをワードクラウドにします</h3>
    <b-container>
      <p v-if="loading">読み込み中(数十秒かかるので気長にまってちょ。。)</p>
      <vue-loading
        v-if="loading"
        type="spin"
        color="#333"
        :size="{ width: '50px', height: '50px' }"
      ></vue-loading>
      <p v-if="imgUrl">こんなツイートをしてるみたい</p>
      <b-img fluid :src="imgUrl" />
    </b-container>
  </b-container>
</template>

<script>
import axios from "axios";
import { VueLoading } from "vue-loading-template";
export default {
  components: {
    VueLoading,
  },
  props: {
    username: String,
  },
  data() {
    return {
      loading: true,
      imgUrl: "",
    };
  },
  created() {
    this.sendDataToAPI();
  },
  methods: {
    sendDataToAPI() {
      axios
        .get(
          "https://us-central1-ryopenguin-9f2e7.cloudfunctions.net/tweetcloud?screen_name=" +
            this.username
        )
        .then((response) => {
          this.imgUrl = response["data"]["img"];
          this.loading = false;
        });
    },
  },
};
</script>