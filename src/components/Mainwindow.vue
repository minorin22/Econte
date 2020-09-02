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
</style>
