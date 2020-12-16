<template>
  <div
    id="box"
    :style="{
      bottom: boxBottom,
    }"
  >
    <i
      class="iconfont icon-yinle"
      :style="{
        top: iconTop,
        'text-align': iconTextAlign,
      }"
      @click="showBox"
    ></i>
    <div class="play">
      <i
        :class="{
          iconfont: true,
          'btn-paly': true,
          'icon-bofang1': isPlay,
          'icon-zanting': !isPlay,
        }"
        ><loading-box
          :style="{
            display: loadingShow,
            top: icon2Top,
          }"
      /></i>
    </div>
    <audio
      id="music"
      src="https://m7.music.126.net/20201009092608/629118dae298ae302fffb9768b99ad75/ymusic/36e3/21e2/20a3/bedc5b2b7de0a8afdbf001fad52c9c30.mp3"
    ></audio>
  </div>
</template>

<script>
import loadingBox from "@/components/public/loading/loading.vue";
export default {
  components: {
    loadingBox,
  },
  data() {
    return {
      isPlay: false,
      show: false,
      boxBottom: "-80px",
      iconTop: "-28px",
      iconTextAlign: "center",
      icon2Top: "-42px",
      loadingShow: "none",
    };
  },
  watch: {
    show(val) {
      if (val) {
        this.boxBottom = "0px";
        this.iconTop = "0";
        this.icon2Top = "-12px";
      } else {
        this.boxBottom = "-80px";
        this.iconTop = "-30px";
        this.icon2Top = "-42px";
      }
    },
    isPlay(val) {
      if (val) {
        this.loadingShow = "block";
        this.iconTextAlign = "left";
      } else {
        this.loadingShow = "none";
        this.iconTextAlign = "center";
      }
    },
  },
  methods: {
    playMusic() {
      if (this.isPlay) {
        document.getElementById("music").play();
        this.loadingShow = "block";
      } else {
        document.getElementById("music").pause();
        this.loadingShow = "none";
      }
      this.isPlay = !this.isPlay;
    },
    showBox() {
      this.show = !this.show;
    },
  },
  mounted() {
    let that = this;
    document.onkeypress = function(e) {
      if (e.code == "Space") {
        that.playMusic();
      }
    };
  },
};
</script>

<style lang="scss">
$defaultColor: #64d3ff;
#box {
  display: flex;
  justify-content: center;
  position: fixed;
  width: 100vw;
  height: 80px;
  bottom: -80px;
  line-height: 50px;
  padding: 0 150px;
  background-color: $defaultColor;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  z-index: 100;
  transition: all 0.3s;
  cursor: pointer;
  .icon-yinle {
    padding: 0 5px;
    box-sizing: border-box;
    position: absolute;
    top: 0px;
    left: 8px;
    width: 40px;
    height: 28px;
    line-height: 30px;
    font-size: 22px;
    transition: all 0.3s;
    color: $defaultColor;
    color: white;
    background-color: $defaultColor;
    border-top-left-radius: 25px;
    border-top-right-radius: 25px;
    opacity: 1;
  }
  .icon-yinle:hover {
    background-color: gray;
    z-index: 10;
    text-align: center !important;
  }
  .play {
    background-color: red;
    width: 800px;
    .iconfont {
      font-size: 40px;
      color: white;
      transition: all 0.3s;
      background-color: rgba(0, 0, 0, 0.4);
      border-radius: 50%;
      cursor: pointer;
    }
  }
}

.loading-box {
  position: absolute;
  top: 0px;
  left: 33px;
  width: 12px;
  height: 8px;
}
</style>
