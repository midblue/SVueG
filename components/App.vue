<template>
  <div id="app">
    <SVueG
      id="testSVG"
    >
      test
    </SVueG>
  </div>
</template>

<script>
import SVueG from './SVueG.vue'

export default {
  components: { SVueG, },
  data () {
    return {}
  },
  computed: {},
  mounted () {},
  methods: {
  }
}
</script>

<style scoped lang="scss">
#app {
  
}

#testSVG {
  width: 800px;
  height: 400px;
}

</style>
