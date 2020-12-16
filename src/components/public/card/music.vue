<template>
  <div class="card-music">
    <ul class="card-list">
      <li class="card" v-for="item in musicList" :key="item.id">
        <div class="card-img">
          <img :src="item.picUrl" alt="" />
          <a href="./songList/songList.html?listId=${musicList[i]}">
            <div class="play"><i class="iconfont icon-iconfontplay"></i></div>
          </a>
        </div>
        <p class="title">{{ item.name }}</p>
        <p class="num">
          播放量：
          {{
            item.playCount > 10000
              ? (item.playCount / 10000).toFixed(2) + "万"
              : item.playCount
          }}
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
.card-music {
  overflow: hidden;
  .card-list {
    width: 100%;
    padding-left: 36px;
    display: flex;
    flex-wrap: wrap;
    justify-content: start;
    position: relative;
    left: 0;
    transition: all 0.3s;
    .card {
      margin-top: 30px;
      margin-right: 36px;
      width: 200px;
      box-sizing: border-box;
      font-size: 16px;
      position: relative;
      .card-img {
        position: relative;
        cursor: pointer;
        img {
          width: 200px;
          height: 200px;
          overflow: hidden;
          transition: 0.1s;
        }
        .play {
          position: absolute;
          background-color: rgba(0, 0, 0, 0.5);
          text-align: center;
          top: -2px;
          bottom: -2px;
          left: -2px;
          right: -2px;
          opacity: 0;
          transition: all 0.3s;
          display: flex;
          justify-content: center;
          align-items: center;
          i {
            font-size: 60px;
            padding: 10px;
            color: white;
            transition: 0.3s;
          }
          i:hover {
            color: $defaultColor;
          }
        }
      }
      .card-img:hover {
        .play {
          opacity: 1;
        }
        img {
          transform: scale(1.01);
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
      .num {
        margin-top: 10px;
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
