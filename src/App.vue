<template>
  <div class="svg_demo">

      <header class="header">
        <div class="menu_toggle">Menu</div>
        <div class="menu_title">Learn SVG Helper</div>
      </header>

      <div class="demo_layout">

        <div class="left_panel code_toolbox">
          <h2 class="code_toolbox-title">HTML Code:</h2>
          
          <pre class="code_toolbox-adjust">

            <code>

              <div class="tag">
                  <span>&lt;svg</span>
              </div>

              <div class="attr" @click="selectedAttr('height')">
                  <div class="attr_wrapper">
                    <span class="attr_name">height</span>
                    <span>="</span>
                    <div class="attr_adjust attr_height">{{ attr_height }}</div>
                    <span>"</span>
                  </div>
              </div>
                
              <div class="attr" @click="selectedAttr('width')">
                  <div class="attr_wrapper">
                    <span class="attr_name">width</span>
                    <span>="</span>
                    <div class="attr_adjust attr_width">{{ attr_width }}</div>
                    <span>"</span>
                  </div>
              </div>

              <div class="attr have_enable">
                  <div class="attr_wrapper" v-bind:class = "(viewbox_enable)?'class_if_is_true':'deactivated'">
                    <span @click="selectedAttr('viewbox_1')" class="attr_name">viewBox</span>
                    <span>="</span>
                    <div @click="selectedAttr('viewbox_1')" class="attr_adjust attr_viewbox_1">{{ attr_viewbox_1 }}</div>
                    <div @click="selectedAttr('viewbox_2')" class="attr_adjust attr_viewbox_2 attr_gap">{{ attr_viewbox_2 }}</div>
                    <div @click="selectedAttr('viewbox_3')" class="attr_adjust attr_viewbox_3 attr_gap">{{ attr_viewbox_3 }}</div>
                    <div @click="selectedAttr('viewbox_4')" class="attr_adjust attr_viewbox_4 attr_gap">{{ attr_viewbox_4 }}</div>
                    <span>"</span>
                  </div>
                  <div class="attr_enable">
                    <input id="enable_viewbox" class="switch" type="checkbox" @click="checkbox_viewbox">
                    <label for="enable_viewbox">enable</label>
                  </div>
              </div>

              <div class="tag">
                  <span v-if="viewbox_enable"> /&gt;</span>
                  <span v-else> /&gt; &lt;/svg&gt;</span>
              </div>

            </code>

            <div class="sliders">
              <div v-if="this.selected == 'height'">
                <p>Height: </p>
                <input v-model="attr_height" type="range" min="50" max="600" class="slider">
              </div>
              <div v-else-if="this.selected == 'width'">
                <p>Width: </p>
                <input v-model="attr_width" type="range" min="50" max="600" class="slider">
              </div>
              <div v-else-if="this.selected == 'viewbox_1'">
                <p>Min-x: </p>
                <input v-model="attr_viewbox.attr1" type="range" min="0" max="5" class="slider">
              </div>
              <div v-else-if="this.selected == 'viewbox_2'">
                <p>Min-y: </p>
                <input v-model="attr_viewbox_2" type="range" min="0" max="5" class="slider">
              </div>
              <div v-else-if="this.selected == 'viewbox_3'">
                <p class="sm_text">Viewbox Width: </p>
                <input v-model="attr_viewbox_3" type="range" min="0" max="10" class="slider">
              </div>
              <div v-else-if="this.selected == 'viewbox_4'">
                <p class="sm_text">Viewbox Height: </p>
                <input v-model="attr_viewbox_4" type="range" min="0" max="10" class="slider">
              </div>
              <div v-else>
                <p class="sm_text">Select an attribute</p>
              </div>
            </div>

          </pre>
        </div>

        <div class="right_panel">

          <div class="demo">
            <svg
              class="svg"
              :height="attr_height"
              :width="attr_width"
              :viewBox="attr_viewbox">
            <circle cx="200" cy="200" r="200"/>
            </svg>
          </div>

        </div>

      </div>
  </div>
</template>

<script>
// import Nav_header from './components/Nav_header.vue'
// import Code_Display from './components/Demo_codedisplay.vue'
// import Result_Display from './components/Demo_resultdisplay.vue'

import $ from "jquery";

export default {
  name: 'App',
  components: {
    // Nav_header,
    // Code_Display,
    // Result_Display
  },
  data() {
      return {
          selected: "",
          attr_height: 500,
          attr_width: 500,
          viewbox_enable: false,
          attr_viewbox_1: 0,
          attr_viewbox_2: 0,
          attr_viewbox_3: 0,
          attr_viewbox_4: 0,
          viewBox: [this.attr_viewbox_1, this.attr_viewbox_2, this.attr_viewbox_3, this.attr_viewbox_4]
      }
  },
  methods: {
    selectedAttr(attr) {

      this.selected = attr;
      var selection = $('.attr_' + attr);

      $('.attr_adjust').removeClass("selected");
      selection.addClass("selected");
  
    },
    checkbox_viewbox() {
      this.viewbox_enable = !this.viewbox_enable;
      console.log(this.viewbox_enable);
    }
  }

  
}
</script>

<style lang="scss">
  @import './design/index.scss';
</style>
