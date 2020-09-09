<template>
  <div class="box" id="storyboard" v-html="body"></div>
</template>

<script>
const { ipcRenderer, remote } = require("electron");
const fs = remote.require("fs");

export default {
  data: function () {
    return {
      bodyBefore: "",
      body: "",
      bodyAfter: "",
    };
  },
  mounted: function () {
    // ファイルを開く
    //Electron側からファイルパスを受け取る
    ipcRenderer.on("openFile", (event, filePath) => {
      console.log(filePath);

      // ファイルデータを読み込む
      if (filePath === "") {
        return "";
      }
      const html = fs.readFileSync(filePath, "utf-8");

      // htmlをbodyとそれ以外に分割する
      this.splitHtml(html);
    });

    // ファイルに保存する
    // Electron側からファイルパスを受け取る
    ipcRenderer.on("saveFile", (event, filePath) => {
      console.log(filePath);

      if (this.htmlText === "") {
        alert("保存するデータがありません");
        return;
      }

      // ファイルに保存する
      const html = this.bodyBefore + this.body + this.bodyAfter;
      fs.writeFileSync(filePath, html, "utf-8");
    });
  },
  methods: {
    splitHtml: function (html) {
      // <body>の後ろの文字の位置
      const startPos = html.indexOf("<body>") + "<body>".length;

      // </body>の前の文字の位置
      const endPos = html.indexOf("</body>");

      // bodyタグで文字列を分割する
      this.bodyBefore = html.slice(0, startPos);
      this.body = html.slice(startPos, endPos);
      this.bodyAfter = html.slice(endPos, html.length);
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