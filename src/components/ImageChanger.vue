<template>
  <div 
    class="app_container" 
    @click="clicked()"
  >
    <icon-base v-if="state===0" icon-name="this is a HOME" :width="800" :height="400"
      ><stet
    /></icon-base>
    <icon-base v-if="state===1" icon-name="this is my HOME" :width="800" :height="400"
      ><hover
    /></icon-base>
    <icon-base v-if="state===2" icon-name="I'm going HOME" :width="800" :height="400"
      ><click
    /></icon-base>
    <button v-html="'Hover'" />
  </div>
</template>

<script>
import { ref } from "vue"
import IconBase from "./IconBase.vue"
import stet from "./icons/stet.vue"
import hover from "./icons/hover.vue"
import click from "./icons/click.vue"

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
    
    function enter(){
      state = 1  
    }
    function exit(){
      state = 0  
    }
    function clicked(){
      state = 2  
    }
    return { state, enter, exit, clicked }
  }
}

</script>

<style>
.app_container {
  max-width: 800px;
  background-color: #fef6d2;
}
</style>