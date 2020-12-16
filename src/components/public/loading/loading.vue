<template>
  <div class="loading-box">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>
</template>

<style>
/**
* 需要父级设置loadding-box宽高
*/
.loading-box {
  transition: all 0.3s;
}
.loading-box span {
  display: inline-block;
  margin: 2.5%;
  width: 20%;
  height: 10%;
  background: lightgreen;
  animation: load 1.04s ease infinite;
}

@keyframes load {
  0%,
  100% {
    height: 20%;
    background: white;
  }
  50% {
    height: 100%;
    margin-top: -60%;
    background: white;
  }
}

.loading-box span:nth-child(2) {
  animation-delay: 0.39s;
}

.loading-box span:nth-child(3) {
  animation-delay: 0.26s;
}

.loading-box span:nth-child(4) {
  animation-delay: 0.13s;
}
</style>
