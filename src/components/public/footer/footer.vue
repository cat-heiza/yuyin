<template>
  <div class="footer"></div>
</template>
<style lang="scss">
.footer {
  margin-top: 40px;
  width: 100%;
  height: 400px;
  background-image: url("../../../assets/image/img.png");
  background-position: center;
  position: relative;
}

.footer::after {
  content: "";
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.5);
}
</style>
