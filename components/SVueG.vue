<template>
  <svg
    :width="width"
    :height="height"
    :viewBox="`0 0 ${width} ${height}`"
    :style="{background: bg}"
    version="1.1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
  >
    <slot :rect="objectRect"></slot>
  </svg>
</template>

<script>

export default {
  components: {},
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
