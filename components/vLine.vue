<template>
  <g>
    <path
      v-if="endX && endY"
      :d="`M${x},${y} L${endX},${endY}`"
      class="line"
      :stroke="color"
      :width="width"
      stroke-linecap="round">
    </path>
    <path
      v-else-if="length && angle"
      :d="`M${x},${y} L${length * Math.cos(angleRad) + x},${length * Math.sin(angleRad) + y}`"
      class="line"
      :stroke="color"
      :width="width"
      stroke-linecap="round">
    </path>
  </g>
</template>

<script>

export default {
  props: {
    color: {
      type: String,
      required: false,
      default: '#999'
    },
    width: {
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
#app {
  
}

</style>
