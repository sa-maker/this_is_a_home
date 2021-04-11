<template>
  <div
    class="app_container"
    @mouseenter="handelEnter()"
    @mouseleave="handelExit()"
    @mousedown="handelDown()"
    @mouseup="handelUp()"
  >
    <icon-base
      v-if="state === 0"
      icon-name="this is a HOME"
      :width="800"
      :height="400"
    >
      <stet />
    </icon-base>
    <icon-base
      v-if="state === 1"
      icon-name="this is my HOME"
      :width="800"
      :height="400"
    >
      <hover />
    </icon-base>
    <icon-base
      v-if="state === 2"
      icon-name="I'm going HOME"
      :width="800"
      :height="400"
    >
      <click />
    </icon-base>
  </div>
</template>

<script>
import { ref } from 'vue'
import IconBase from './IconBase.vue'
import stet from './icons/stet.vue'
import hover from './icons/hover.vue'
import click from './icons/click.vue'

export default {
  name: 'ImageChanger',
  components: {
    IconBase,
    stet,
    hover,
    click
  },
  setup() {
    var state = ref(0)
    var down = false

    function handelEnter() {
      if (!down) {
        state.value = 1
      }
    }
    function handelExit() {
      state.value = 0
    }
    function handelDown() {
      down = true
      state.value = 2
    }
    function handelUp() {
      down = false
      state.value = 1
    }
    return { state, handelEnter, handelExit, handelDown, handelUp }
  }
}
</script>

<style>
.app_container {
  cursor: pointer;
  max-width: 600px;
  background-color: #fef6d2;
  margin: 0px auto;
  padding-top: 1em;
  padding-bottom: 1em;
}
</style>
