<template>
  <div class="about">
    <h1 v-bind="this.val"></h1>
    <a :href="url">本日限免!</a>
  </div>
</template>

<script>
export default {
  name: "LiuduanAboutView",
  data() {
    return {
      url: "https://www.bilibili.com/"
    };
  },
  // <template>
  //   <div class="about">
  //     <h1>This is an about page</h1>
  //   </div>
  // </template>
  mounted() {},

  methods: {}
};
</script>

<style scoped>
.xuan {
  border: none !important;
}
</style>