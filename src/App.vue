<template>
  <div id="app">
    <router-view />
    <music-box />
  </div>
</template>

<script>
import musicBox from "@/components/musicBox/box.vue";
export default {
  name: "App",
  components: {
    musicBox,
  },
};
</script>
<style lang="scss">
@import "@/assets/css/public/reset.scss";
@import "http://at.alicdn.com/t/font_1796518_8kiu6nyf9j5.css";
</style>
