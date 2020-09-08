<template>
  <div class="box" id="storyboard" v-html="htmlText"></div>
</template>

<script>
const { ipcRenderer, remote } = require("electron");
const fs = remote.require("fs");

export default {
  data: function () {
    return {
      filePath: "",
    };
  },
  computed: {
    htmlText: function () {
      if (this.filePath === "") {
        return "";
      }

      // ファイルデータを読み込む
      const data = fs.readFileSync(this.filePath, "utf-8");

      // bodyのみを取り出す
      const bodyText = this.extractText(data, "<body>", "</body>");
      return bodyText;
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
  methods: {
    extractText: function (text, start, end) {
      // startの文字の位置
      const startPos = text.indexOf(start) + start.length;

      // endの文字の位置
      const endPos = text.indexOf(end);

      // 間の文字列を切り取る
      const result = text.slice(startPos, endPos);

      return result;
    },
  },
};
</script>

<style scoped>
.box >>> .storyboard {
  display: grid;
}
.box >>> .coma {
  display: grid;
  grid-template-columns: 60px 192px auto auto 100px;
  min-height: 108px;
}
.box >>> .head {
  background-color: #fff;
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  z-index: 1000;
  min-height: 28px !important;
  border: 1px solid #00000038;
}
.box >>> .cut,
.box >>> .picture,
.box >>> .action,
.box >>> .dialogue,
.box >>> .time {
  border: 1px solid #00000038;
}
.box >>> .head .cut,
.box >>> .head .picture,
.box >>> .head .action,
.box >>> .head .dialogue,
.box >>> .head .time {
  border: none;
}
.box >>> .picture {
  line-height: 0;
  background-color: #fff;
}
.box >>> .action,
.box >>> .dialogue {
  min-width: 140px;
}
.box >>> h4 {
  margin: 2px 4px;
  line-height: 24px;
}
.box >>> img {
  position: relative;
  z-index: 2;
  zoom: 0.1;
}
.box {
  color: black;
}
</style>