<template>
  <div class="box" id="toolproperty">
    <h5 class="tool_title"><font-awesome-icon icon="paint-brush" /> Tool Property</h5>
    <dl class="property">
      <dt>TYPE</dt>
      <dd>
        <select>
          <option>Watercolor</option>
          <option>Watercolor2</option>
          <option>Watercolor3</option>
        </select>
      </dd>
      <dt>SIZE</dt>
      <dd>
        <div class="slider">
          <input type="range"><input type="value">
        </div>
      </dd>
      <dt>SMOOTH</dt>
      <dd>
        <div class="slider">
          <input type="range"><input type="value">
        </div>
      </dd>
      <dt>PRESSURE</dt>
      <dd>
        <input type="checkbox" checked id="checkbox01" />
        <label for="checkbox01" class="checkbox"></label>
      </dd>
    </dl>
  </div>
</template>

<script>

</script>

<style scoped>
.property dd{
  margin-left: 76px;
}
.checkbox {
  margin-left: 90px;
}
</style>