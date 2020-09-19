<template>
    
    <div id="container">
      <Toolbar></Toolbar>
      <div class="left_tools">
        <Outline></Outline>
        <Toolproperty></Toolproperty>
        <Color></Color>
      </div>
      <Storyboard></Storyboard>
      <div class="right_tools">
        <Effect></Effect>
        <Camerawork></Camerawork>
        <Layer></Layer>
      </div>
      <Timeline></Timeline>
      <footer>
        <h1 class="title">Footer</h1>
      </footer>
    </div>
  
</template>

<script>
import Toolbar from './Toolbar'
import Outline from './Outline'
import Toolproperty from './Toolproperty'
import Color from './Color'
import Storyboard from './Storyboard'
import Effect from './Effect'
import Camerawork from './Camerawork'
import Layer from './Layer'
import Timeline from './Timeline'
export default {
  components: {
    Toolbar,Outline,Toolproperty,Color,Storyboard,Effect,Camerawork,Layer,Timeline
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
@import "../main.css";
body {
  background-color: #2D2D2D;
}
body, select, .vc-input__input,input[type="value"], .vc-input__label {
  color: #FFFFFFE0!important;
}
#storyboard, select, input[type="value"], input[type="range"]::-webkit-slider-thumb, .checkbox, .vc-input__input {
  background-color: #212121;
}
.box, select, input[type="value"], .checkbox:after, .vc-input__input {
  border: 1px solid #00000038;
}
</style>
