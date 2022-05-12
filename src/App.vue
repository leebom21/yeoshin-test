<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">깃허브의 이슈 리스트</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: 맑은 고딕, malgun gothic, AppleGothicNeoSD, Apple SD 산돌고딕 Neo,
    Microsoft NeoGothic, Droid sans, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  background: #fff6fa;
}

#nav {
  padding: 4%;
  a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;

    &.router-link-exact-active {
      color: #222;
    }
  }
}
</style>
