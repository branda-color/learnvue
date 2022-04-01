<template>
  <div class="catch">
    <h1>This is a catch page</h1>
    <div>{{ info.to }}</div>
    <div>{{ info.status }}</div>
  </div>
</template>

<script>
export default {
  name: "catch-data",
  data() {
    return {
      text: "helloworld",
      info: {},
    };
  },
  async created() {
    // GET request using fetch with async/await
    const response = await fetch("https://uat.tickup.work/api/tovue");
    const data = await response.json();
    this.info = data;
  },
};
</script>
