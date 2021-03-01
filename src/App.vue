<template>
  <image-changer class="app" />
</template>

<script>
import ImageChanger from "./components/ImageChanger.vue"

export default {
  name: "App",
  components: {
    ImageChanger
  }
}
</script>

<style>
.app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
