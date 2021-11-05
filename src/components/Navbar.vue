<template>
  <div class="nav__bar">
    <router-link to="/" class="nav__logo nav__link">Todolist</router-link>
    <div class="nav__items">
      <router-link to="/about" class="nav__item nav__link">About</router-link>
      <router-link to="/my-page" class="nav__item nav__link">
        MyPage
      </router-link>
    </div>
  </div>
</template>

<style scoped>
.nav__bar {
  height: 150px;
  display: flex;
  justify-content: space-between;
  align-items: stretch;
  background-color: deepskyblue;
  font-size: 50px;
}
.nav__link {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  color: #eee;
  text-decoration: none;
}
.nav__link:visited {
  color: #eee;
}
.nav__link:hover {
  font-weight: bold;
  color: #fff;
}
.nav__logo {
  width: 300px;
}
.nav__items {
  display: flex;
}
.nav__item {
  width: 300px;
  border-left: 1px solid #eee;
}
</style>
