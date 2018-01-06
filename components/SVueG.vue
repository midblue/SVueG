<template>
  <svg
    :width="width"
    :height="height"
    :viewBox="`0 0 ${width} ${height}`"
    :style="`background: ${bg};`"
    version="1.1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
  >
    <vLine
      :x="50"
      :y="50"
      :endX="100"
      :endY="100"
    />
    <vLine
      :x="50"
      :y="70"
      :length="100"
      :angle="10"
    />
    <vEllipse
      :x="90"
      :y="70"
      :width="30"
      :height="50"
      :angle="45"
    />
  </svg>
</template>

<script>
import vLine from './Line'
import vEllipse from './Ellipse'

export default {
  components: { vLine, vEllipse },
  props: {
    bg: {
      type: String,
      required: false,
      default: null,
    },
  },
  data () {
    return {
      objectRect: {
        width: 0,
        height: 0,
      },
    }
  },
  computed: {
    width () { return this.objectRect.width },
    height () { return this.objectRect.height },
  },
  mounted () {
    this.$nextTick(this.updateObjectRect)
  },
  methods: {
    updateObjectRect () { this.objectRect = this.$el.getBoundingClientRect() }
  }
}
</script>

<style scoped lang="scss">

</style>
