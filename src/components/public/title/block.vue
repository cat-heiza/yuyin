<template>
  <div class="title-block">
    <h2>{{ name }}</h2>
    <router-link class="more" :to="moreUrl">更多>></router-link>
  </div>
</template>

<script>
export default {
  props: ["name", "moreUrl"],
};
</script>

<style lang="scss">
$defaultColor: #64d3ff;
$fontColor: #666;

.title-block {
  padding: 20px 0;
  color: $fontColor;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  position: relative;
  h2 {
    font-size: 24px;
  }
  .more {
    font-size: 14px;
    color: $fontColor;
    text-decoration: none;
  }
}
.title-block::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 4px;
  background-color: $defaultColor;
}
</style>
