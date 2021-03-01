<template>
  <svg xmlns="http://www.w3.org/2000/svg"
    width="80%"
    height="100%"
    :viewBox="view_box"
    :aria-labelledby="iconName"
    role="presentation"
  >
    <title
      :id="iconName"
      lang="en"
    >{{ iconName }}</title>
    <g :fill="iconColor">
      <slot />
    </g>
  </svg>
</template>
<script>

export default {
  name: 'IconBase',
  props: {
    iconName: {
      type: String,
      default: 'box'
    },
    width: {
      type: [Number, String],
      default: 18
    },
    height: {
      type: [Number, String],
      default: 18
    },
    iconColor: {
      type: String,
      default: 'currentColor'
    }
  },
  setup(){
    // const view_box = '0 0 ' + props.width + ' ' + props.height 
    const view_box = '0 0 1000 600'
    return { view_box };
  }
  // methods:
}
</script>

<style scoped>
svg {
  display: inline-block;
  vertical-align: baseline;
  margin-bottom: -2px; /* yes, I'm that particular about formatting */
}
</style>