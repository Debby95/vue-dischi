<template>
  <div id="app">
    <TheHeader></TheHeader>
    <TheMusic></TheMusic>
    <TheMusicList></TheMusicList>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheMusic from './components/TheMusic.vue'
import TheMusicList from './components/TheMusicList.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    TheMusic,
    TheMusicList,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-color: #1E2D3B;
}
</style>
