<template>
  <main>
    <nav>
      <ul>
        <li>
          <nuxt-link to="/screen-1">Screen 1</nuxt-link>
        </li>
      </ul>
    </nav>
  </main>
</template>

<script>
  export default {
    methods: {
      toggleFullScreen() {
        if (!document.fullscreenElement) {
            document.documentElement.requestFullscreen();
        } else {
          if (document.exitFullscreen) {
            document.exitFullscreen();
          }
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  main {
    width: 100%;
    height: 100%;
    position: absolute;
    padding: 40px;
  }
</style>
