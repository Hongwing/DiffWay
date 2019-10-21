// Home Page
<template>
  <div class="dw-home">
    <div class="dw-home-tools">
      <button @click="handleDiff">点击Diff</button>
    </div>
    <div class="dw-home-panel">
      <dw-diffpanel></dw-diffpanel>
    </div>
  </div>
</template>

<script>
import DwDiffpanel from "@/components/panel/dw-diffpanel";
export default {
  name: "DWHome",
  components: {
    DwDiffpanel
  },
  data: () => {
    return {
      name: "DW Home"
    };
  },
  methods: {
      handleDiff: () => {
          
      }
  }
};
</script>

<style lang="stylus">
.dw-home {
  $dw-border = 1px solid rgba(0, 0, 0, 0.15);
  $dw-shadow = 2px 20px 20px rgba(0, 0, 0, 0.15);
  padding: 0 20px;

  .dw-home-tools {
    border: $dw-border;
    box-shadow: $$dw-shadow;
    border-radius: 4px;
    padding: 8px 12px;
    display: flex;
    justify-content: flex-start;

    button {
      font-size: 1.2rem;
      border-radius: 4px;
      background-color: white;
      color: #cb1173;
      padding: 4px 8px;
      outline: none;
    }
  }

  .dw-home-panel {
    border: $dw-border;
    box-shadow: $$dw-shadow;
    border-radius: 4px;
    margin-top: 20px;
  }
}
</style>