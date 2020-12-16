<template>
  <div class="user">
    <ul>
      <li class="login">
        <router-link :to="{ path: '/login' }"
          ><button class="btn-login">登录</button></router-link
        >
      </li>
      <li class="user-info">
        <img src="" alt="" class="avatar" />
        <ul class="info">
          <li class="setting">个人设置</li>
          <li class="sign-out">退出登录</li>
        </ul>
      </li>
    </ul>
  </div>
</template>
