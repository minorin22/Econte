<template>
  <div class="box" id="storyboard">
    <div>{{htmlText}}</div>
  </div>
</template>

<script>
const { ipcRenderer } = require("electron");

export default {
  data: function () {
    return {
      filePath: "",
    };
  },
  computed: {
    htmlText: function () {
      // ファイルデータを読み込む

      // 関係ないところをカットする

      return this.filePath + "html";
    },
  },
  mounted: function () {
    // Electron側からファイルパスを受け取る
    ipcRenderer.on("openFile", (event, filePath) => {
      console.log(filePath);
      // filepathをdataにセットする
      this.filePath = filePath;
    });
  },
};
</script>

<style scoped>
</style>