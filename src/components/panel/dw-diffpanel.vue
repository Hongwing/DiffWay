<template>
  <div class="dw-diffpanel">
    <div class="dw-panel">
      <textarea v-model="leftContent" name="l-panel" class="panel" :disabled="showDiff"></textarea>
    </div>

    <div class="line"></div>

    <div v-if="!showDiff" class="dw-panel">
      <textarea v-model="rightContent" name="r-panel" class="panel"></textarea>
    </div>

    <div class="dw-panel" v-else>
      <pre v-html="rightContent" class="panel"></pre>
    </div>
  </div>
</template>

<script>
import TextDiff from "text-diff";

export default {
  name: "DWDiffpanel",
  props: {
    showDiff: {
      type: Boolean,
      default: false
    }
  },
  data: () => {
    return {
      leftContent: "",
      rightContent: ""
    };
  },
  watch: {
    showDiff: function(n, o) {
      console.info("changed toggle", o, n);
      if (n) {
        this.execDiff();
      } else {
        this.leftContent = this.rightContent = "";
      }
    }
  },
  created() {},
  methods: {
    execDiff: function() {
      const diff = new TextDiff();
      const currentDiff = diff.main(this.rightContent, this.leftContent);
      this.rightContent = diff.prettyHtml(currentDiff);
      if (currentDiff.length === 1 && currentDiff[0][0] === 0) {
        alert("一模一样哦！");
      }
    }
  }
};
</script>

<style lang="stylus">
.dw-diffpanel {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;

  .dw-panel {
    min-height: 480px;
    width: 580px;
    margin: 10px;

    .panel {
      font-family: monospace;
      width: 100%;
      height: 480px;
      overflow-y: scroll;
      font-size: 1.2rem;
      border: none;
      outline: none;
      letter-spacing: 0.1rem;
      text-align: left;
      border-top: 2px dashed #cb1173;
      padding-top: 8px;
    }

    &:nth-child(2) {
      border-right: none;
    }
  }

  .line {
    width: 2px;
    height: 480px;
    background-color: #cb1173;
  }

  del {
    background-color: #cb1173;
    color: white;
    text-decoration: none;
  }

  ins {
    text-decoration: none;
  }
}
</style>