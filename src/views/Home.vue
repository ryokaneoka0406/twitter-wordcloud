<template>
  <b-container class="mt-3">
    <h3>好きなTwitterアカウントのツイートをワードクラウドにします</h3>
    <b-container>
      <div>
        <p>Twitterアカウント名を入力</p>
        <b-form-input v-model="username" placeholder="@以降のユーザー名"></b-form-input>
        <b-button class="mt-3 float-right" variant="primary" @click="sendDataToResult">送信</b-button>
      </div>
    </b-container>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      username: "",
    };
  },
  methods: {
    sendDataToResult() {
      this.$router.push({
        name: "result",
        params: { username: this.username },
      });
    },
  },
};
</script>