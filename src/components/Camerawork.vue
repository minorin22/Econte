<template>
  <div class="box" id="camerawork">
    <h5 class="tool_title"><font-awesome-icon icon="video" /> Camera Work</h5>
    <table>
      <tr>
        <td class="td1">POSITION</td>
        <td class="td2">IN</td>
        <td class="td3">X</td>
        <td class="td4"><input type="value"></td>
        <td class="td5">Y</td>
        <td class="td6"><input type="value"></td>
      </tr>
      <tr>
        <td class="td1"></td>
        <td class="td2">OUT</td>
        <td class="td3">X</td>
        <td class="td4"><input type="value"></td>
        <td class="td5">Y</td>
        <td class="td6"><input type="value"></td>
      </tr>
      <tr>
        <td class="td1">SIZE</td>
        <td class="td2">IN</td>
        <td class="td3"></td>
        <td class="td4"><input type="value"></td>
        <td class="td5"></td>
        <td class="td6"></td>
      </tr>
      <tr>
        <td class="td1"></td>
        <td class="td2">OUT</td>
        <td class="td3"></td>
        <td class="td4"><input type="value"></td>
        <td class="td5"></td>
        <td class="td6"></td>
      </tr>
    </table>
  </div>
</template>

<script>

</script>

<style scoped>
table {
  margin: 4px 10px;
}
tr {
  height: 28px;
}
td {
  padding: 0;
}
.td1 {
  width: 68px;
}
.td2 {
  width: 32px;
  text-align: right;
}
.td3,.td5{
  width: 22px;
  text-align: center;
}
.td4, .td6{
  width: 38px;
}
input[type="value"] {
  -webkit-appearance: none;
   -moz-appearance: none;
        appearance: none;
  background-color: #fff;
  border: 1px solid #00000038;
  height: 18px;
  width: 38px;
}
</style>