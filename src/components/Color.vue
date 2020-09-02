<template>
  <div class="box" id="color">
    <h5 class="tool_title"><font-awesome-icon icon="palette" /> Color</h5>
    <sketch-picker :value="colors"></sketch-picker>
  </div>
</template>

<script>
import { Sketch } from 'vue-color'
export default({
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

<style scoped>
.vc-sketch {
  background: transparent !important;
  border-radius: 0% !important;
  box-shadow: none !important;
  padding-top: 0 !important;
}
</style>