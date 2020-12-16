<template>
  <div class="card-album">
    <ul class="card-list">
      <li class="card" v-for="item in musicList" :key="item.id">
        <div class="card-img">
          <img :src="item.picUrl" alt="" />
          <a href="./songList/songList.html?listId=${musicList[i]}">
            <div class="play"><i class="iconfont icon-bofang1"></i></div>
          </a>
        </div>
        <p class="title">{{ item.name }}</p>
        <p class="user">
          <span v-for="(artist, index) in item.artists" :key="artist.id">
            <span v-if="index != 0"> / </span>
            {{ artist.name }}
          </span>
        </p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["musicList"],
};
</script>

<style lang="scss">
$defaultColor: #64d3ff;
.card-album {
  overflow: hidden;
  .card-list {
    width: 100%;
    margin-top: 20px;
    padding-left: 38px;
    padding-bottom: 38px;
    display: flex;
    flex-wrap: wrap;
    justify-content: start;
    position: relative;
    left: 0;
    transition: all 0.3s;
    background-color: #eee;
    .card {
      margin-top: 28px;
      margin-right: 36px;
      width: 200px;
      box-sizing: border-box;
      font-size: 16px;
      position: relative;
      .card-img {
        position: relative;
        cursor: pointer;
        img {
          width: 177px;
          height: 177px;
          overflow: hidden;
          transition: 0.1s;
        }
        .play {
          position: absolute;
          text-align: center;
          bottom: 6px;
          right: 28px;
          opacity: 0;
          transition: all 0.3s;
          display: flex;
          flex-direction: row-reverse;
          .iconfont {
            width: 34px;
            height: 34px;
            line-height: 34px;
            font-size: 30px;
            color: white;
            transition: 0.3s;
            background-color: rgba(0, 0, 0, 0.5);
            border-radius: 50%;
          }
          .iconfont:hover {
            color: $defaultColor;
          }
        }
      }
      .card-img::after {
        content: "";
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-image: url("../../../assets/image/album_cover.png");
        background-size: 100% 100%;
      }
      .card-img:hover {
        .play {
          opacity: 1;
          z-index: 1;
        }
      }
      .title {
        margin-top: 10px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        cursor: pointer;
      }

      .title:hover {
        text-decoration: underline;
      }
      .user {
        margin-top: 10px;
        width: 100%;
        font-size: 12px;
        color: #666;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }
    }
  }
}
</style>
