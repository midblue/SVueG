<template>
  <ellipse
    class="ellipse"
    :stroke="stroke"
    :stroke-width="strokeWidth"
    :fill="fill"
    :cx="x"
    :cy="y"
    :rx="width / 2"
    :ry="height / 2"
    >
  </ellipse>
</template>

<script>
//:transform="`rotate(${angle})`"
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
      default: 1
    },
    fill: {
      type: String,
      required: false,
      default: 'rgba(0,0,0,.2)'
    },
    x: Number,
    y: Number,
    width: {
      type: Number,
      required: false,
      default: 1
    },
    height: {
      type: Number,
      required: false,
      default: 1
    },
    angle: {
      type: Number,
      required: false,
      default: 0
    },
    rect: {
      type: DOMRect,
      required: false
    }
  },
  data () {
    return {}
  },
  computed: {},
  mounted () {},
  methods: {}
}
</script>

<style scoped lang="scss">

</style>
