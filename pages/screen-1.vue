<template>
  <main :class="fullScreen ? 'fullscreen' : ''">
    <h1>Pure hair screen 1</h1>
    <section class="button_wrapper">
      <button @click="toggleFullScreen">{{ fullScreen ? 'exit full screen' : 'full screen' }}</button>
    </section>
  </main>
</template>

<script>
  export default {
    data() {
      return {
        fullScreen: false,
      }
    },
    methods: {
      toggleFullScreen() {
        if (!document.fullscreenElement) {
            document.documentElement.requestFullscreen();
            this.fullScreen = true
        } else {
          if (document.exitFullscreen) {
            document.exitFullscreen();
            this.fullScreen = false
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
    position: fixed;
    top: 0;
    left: 0;
    background: salmon;
  }
  .button_wrapper {
    width: 300px;
    height: 300px;
    background: seagreen;
    position: absolute;
    bottom: 0;
    right: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    &:hover {
      button {
        display: block;
      }
    }
  }
  button {
    display: block;
    padding: 20px 30px;
    font-size: 32px;
    display: none;
    cursor: pointer;
  }
</style>
