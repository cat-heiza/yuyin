<template>
  <div class="header">
    <my-nav></my-nav>
    <div>
      <my-search-bar></my-search-bar>
      <my-user></my-user>
    </div>
  </div>
</template>
<script>
import myNav from "@/components/public/header/nav.vue";
import mySearchBar from "@/components/public/header/searchBar.vue";
import myUser from "@/components/public/header/user.vue";

export default {
  components: {
    myNav,
    mySearchBar,
    myUser,
  },
};
</script>

<style lang="scss">
@import "@/assets/css/public/header/index.scss";
</style>
