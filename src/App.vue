<template>
  <div class="svg_demo">
    <Nav_header />
    <div class="demo">
      <Code_Display />
      <Result_Display />
    </div>
  </div>
</template>

<script>
import Nav_header from './components/Nav_header.vue'
import Code_Display from './components/Demo_codedisplay.vue'
import Result_Display from './components/Demo_resultdisplay.vue'

export default {
  name: 'App',
  components: {
    Nav_header,
    Code_Display,
    Result_Display
  }
}
</script>

<style lang="scss">
  @import './design/index.scss';
</style>
