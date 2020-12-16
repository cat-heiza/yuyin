<template>
  <div class="title-music-list">
    <h2>{{ name }}</h2>
    <loading-box />
  </div>
</template>

<script>
export default {
  props: ["name"],
};
</script>

<style lang="scss">
$defaultColor: #64d3ff;
$fontColor: #666;
.title-music-list {
  padding: 20px 0;
  color: $fontColor;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  position: relative;
  h2 {
    font-size: 28px;
  }
  .more {
    font-size: 14px;
    color: $fontColor;
    text-decoration: none;
  }
}
.title-music-list::after {
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
