<template>
  <div class="header-nav">
    <router-link :to="{ path: '/index' }" class="header-logo"
      >LingeringVoice余音</router-link
    >
    <ul>
      <li><router-link :to="{ path: '/musicList' }">歌单</router-link></li>
      <li><router-link :to="{ path: '/' }">榜单</router-link></li>
      <li><router-link :to="{ path: '/' }">MV</router-link></li>
      <li><router-link :to="{ path: '/' }">新碟</router-link></li>
      <li><router-link :to="{ path: '/' }">歌手</router-link></li>
      <li><router-link :to="{ path: '/' }">票务</router-link></li>
      <li><router-link :to="{ path: '/' }">我的</router-link></li>
    </ul>
  </div>
</template>
