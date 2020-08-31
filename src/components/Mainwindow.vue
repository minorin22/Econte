<template>
    <body>
    <div id="container">
      <div class="box" id="toolbar">
        <font-awesome-icon class="tool_icon" icon="mouse-pointer" />
        <font-awesome-icon class="tool_icon" icon="paint-brush" />
        <font-awesome-icon class="tool_icon" icon="pen-fancy" />
        <font-awesome-icon class="tool_icon" icon="eraser" />
        <font-awesome-icon class="tool_icon" icon="eye-dropper" />
        <font-awesome-icon class="tool_icon" icon="search" />
      </div>
      <div class="left_tools">
        <div class="box" id="outline">
          <h5 class="tool_title"><font-awesome-icon icon="list" /> Outline</h5>
        </div>
        <div class="box" id="toolproperty">
          <h5 class="tool_title"><font-awesome-icon icon="paint-brush" /> Tool Property</h5>
        </div>
        <div class="box" id="color">
          <h5 class="tool_title"><font-awesome-icon icon="palette" /> Color</h5>
          <sketch-picker :value="colors"></sketch-picker>
        </div>
      </div>
      <div class="box" id="storyboard">
      </div>
      <div class="right_tools">
        <div class="box" id="effect">
          <h5 class="tool_title"><font-awesome-icon icon="magic" /> Effect</h5>
        </div>
        <div class="box" id="camerawork">
          <h5 class="tool_title"><font-awesome-icon icon="video" /> Camera Work</h5>
        </div>
        <div class="box" id="layer">
          <h5 class="tool_title"><font-awesome-icon icon="layer-group" /> Layer</h5>
        </div>
      </div>
      <div class="box" id="timeline">
        <h5 class="tool_title"><font-awesome-icon icon="film" /> Timeline</h5>
      </div>
      <footer class="toolbar toolbar-footer">
        <h1 class="title">Footer</h1>
      </footer>
    </div>
  </body>
</template>

<script>
import { Sketch } from 'vue-color'
//const VueColor = window.VueColor,
//      Sketch = VueColor.Sketch;
export default({
  el: '#app',
  components: {
   'sketch-picker': Sketch,
  },
  data() {
  return {
   colors: {
     hex: '#1f32a6',
     a: 1
   }
    }
 }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
@import "../../photon/css/photon.css";
@import "../main.css";

.vc-sketch {
  background: transparent !important;
  border-radius: 0% !important;
  box-shadow: none !important;
  padding-top: 0 !important;
}
</style>
