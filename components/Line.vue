<template>
  <path
    v-if="(endX && endY) || (length && angle)"
    class="line"
    :d="endX && endY ? 
      `M${x},${y} L${endX},${endY}`
      : length && angle ? 
      `M${x},${y} L${length * Math.cos(angleRad) + x},${length * Math.sin(angleRad) + y}`
      : ''"
    :stroke="stroke"
    :width="strokeWidth"
    stroke-linecap="round">
  </path>
</template>

<script>

export default {
  props: {
    stroke: {
      type: String,
      required: false,
      default: '#999'
    },
    strokeWidth: {
      type: Number,
      required: false,
      default: 1,
    },
    linecap: {
      type: String,
      required: false,
      default: 'square'
    },
    x: Number,
    y: Number,
    endX: {
      type: Number,
      required: false
    },
    endY: {
      type: Number,
      required: false
    },
    length: {
      type: Number,
      required: false
    },
    angle: {
      type: Number,
      required: false,
    },
    rect: {
      type: DOMRect,
      required: false
    }
  },
  data () {
    return {}
  },
  computed: {
    angleRad () { return this.angle ? this.degtoRad(this.angle) : 0}
  },
  mounted () {},
  methods: {
    degtoRad (deg) {
      return deg * 0.01745329252
    },
  }
}
</script>

<style scoped lang="scss">

</style>
