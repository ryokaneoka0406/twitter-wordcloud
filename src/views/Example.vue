<template>
  <b-container class="mt-3">
    <h3>Examples</h3>
    <b-container>
      <p>
        <a href="https://mobile.twitter.com/ryopenguin">作者のTwitter</a>
      </p>
      <b-img fluid :src="testUrl" />
    </b-container>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      testUrl:
        "https://storage.googleapis.com/tweet-cloud/ryopenguin_wordcloud.png",
    };
  },
};
</script>
