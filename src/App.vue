<template>
  <image-changer class="app" />
</template>

<script>
import ImageChanger from './components/ImageChanger.vue'

export default {
  name: 'App',
  components: {
    ImageChanger
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #fef6d2;
  width: 100%;
}
</style>
