<template>
  <div id="app">
    <SVueG
      id="testSVG"
    >
      <g slot-scope="svgProps">
        <vLine
          :x="r(svgProps.rect.width)"
          :y="r(svgProps.rect.height)"
          :endX="r(svgProps.rect.width)"
          :endY="r(svgProps.rect.height)"
        />
        <vLine
          :x="r(svgProps.rect.width)"
          :y="r(svgProps.rect.height)"
          :length="r(1000)"
          :angle="r(360)"
        />
        <vEllipse
          :x="r(svgProps.rect.width)"
          :y="r(svgProps.rect.height)"
          :width="r(svgProps.rect.width)"
          :height="r(svgProps.rect.height)"
          :angle="r(180)"
        />
        {{svgProps}}
      </g>
    </SVueG>
  </div>
</template>

<script>
import SVueG from './SVueG.vue'
import vLine from './Line'
import vEllipse from './Ellipse'

export default {
  components: { SVueG, vLine, vEllipse },
  data () {
    return {}
  },
  computed: {},
  mounted () {},
  methods: {
    r (max) {
      return Math.floor(Math.random() * max)
    },
  }
}
</script>

<style scoped lang="scss">
#app {
  width: 100vw;
  height: 100vh;
}

#testSVG {
  width: 100%;
  height: 100%;
}

</style>
