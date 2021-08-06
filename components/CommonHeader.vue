<template>
  <header>
    <img src="img/logo.png" width="200px">
      <ul class="menu-group">
        <li class="menu-item" v-if="!$auth.loggedIn">
          <NuxtLink to="/register">新規登録</NuxtLink>
        </li>
        <li class="menu-item" v-if="!$auth.loggedIn">
          <NuxtLink to="/login">ログイン</NuxtLink>
        </li>
        <!-- <li class="menu-item" v-else>
          <a @click="logout">Logout</a>
        </li> -->
      </ul>
  </header>
</template>


<style>

header {
  display: flex;
  height: 100px;
  padding: 0 50px;
  margin-bottom: 30px;
  align-items: center;
}


.menu-item {
  list-style: none;
  display: inline-block;
  padding: 10px;
}

.menu-item a {
  color: black;
  text-decoration: none;
  cursor: pointer;
  color: white;
}
</style>
