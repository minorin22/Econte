<template>
  <div class="box" id="effect">
    <h5 class="tool_title"><font-awesome-icon icon="magic" /> Effect</h5>
    <dl class="property">
      <dt>FADE IN</dt>
      <dd>
        <select>
          <option>None</option>
          <option>White In</option>
          <option>Black In</option>
        </select>
      </dd>
      <dt>DURATION</dt>
      <dd>
        <div class="slider">
          <input type="range"><input type="value">
        </div>
      </dd>
      <dt>FADE OUT</dt>
      <dd>
        <select>
          <option>None</option>
          <option>White Out</option>
          <option>Black Out</option>
        </select>
      </dd>
      <dt>DURATION</dt>
      <dd>
        <div class="slider">
          <input type="range"><input type="value">
        </div>
      </dd>
    </dl>
  </div>
</template>

<script>

</script>

<style scoped>
.property dd{
  margin-left: 80px;
}
</style>