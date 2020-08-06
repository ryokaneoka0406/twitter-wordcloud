<template>
  <b-container class="mt-3">
    <h3>好きなTwitterアカウントのツイートをワードクラウドにします</h3>
    <b-container>
      <p>Twitterアカウント名を入力</p>
      <b-form-input v-model.trim="username" placeholder="@以降のユーザー名" :state="validation"></b-form-input>
      <b-form-invalid-feedback v-if="error">{{error}}</b-form-invalid-feedback>
      <b-button class="mt-3 float-right" variant="primary" @click="sendDataToResult">送信</b-button>
    </b-container>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      validation: null,
      error: null,
    };
  },
  watch: {
    // validationをwatch。初期値をnullにするためにcomputedではなくwatch
    username: function (val) {
      const re = /^\w+$/;
      if (val !== "" && re.test(val)) {
        this.validation = true;
      } else if (val === "") {
        this.validation = false;
        this.error = "ユーザー名は必須です";
      } else if (!re.test(val)) {
        this.validation = false;
        this.error = "Twitterアカウントで使えない文字が入っています";
      }
    },
  },
  methods: {
    sendDataToResult() {
      if (this.validation) {
        this.$router.push({
          name: "result",
          params: { username: this.username },
        });
      } else {
        // 入力せずに送信した場合
        this.validation = false;
        this.error = "ユーザー名は必須です";
      }
    },
  },
};
</script>

