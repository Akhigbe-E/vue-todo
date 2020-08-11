<template>
  <div class="about">
    <h1 class="about-header">About</h1>
    <p>
      This is the <b>BasicTodos app</b> . A basic app I built while learning
      Vue. It uses Vue (😅 obviously), vue-router, axios and gets todos from
      jsonplaceholder. Felt cute, might live in Netlify later 💁🏾‍♀️.
    </p>
    <hr />
    <p>
      If you're a recruiter, fear not, your site won't look like this if I'm
      there 🙂.
    </p>
  </div>
</template>

<script>
  export default {
    // created() {
    //   console.log(this.$route.params);
    // },
  };
</script>

<style scoped>
  .about h1 {
    margin: 10px 0px;
  }
  .about p {
    text-align: center;
    max-width: 1000px;
    margin: 0px auto;
    line-height: 30px;
  }
  .about hr {
    margin: 20px 0px;
  }
</style>
