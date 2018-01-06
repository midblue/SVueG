<template>
  <svg
    :width="width"
    :height="height"
    :viewBox="`0 0 ${width} ${height}`"
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
  </svg>
</template>

<script>
import vLine from './vLine'

export default {
  components: { vLine, },
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
#app {
  
}

</style>
