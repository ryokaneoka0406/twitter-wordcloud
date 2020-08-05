<template>
  <b-container class="mt-3">
    <h3>好きなTwitterアカウントのツイートをワードクラウドにします</h3>
    <b-container>
      <div>
        <div class="mt-3">Debug: {{ username }}</div>
      </div>
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