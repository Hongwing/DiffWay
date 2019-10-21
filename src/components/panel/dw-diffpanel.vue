<template>
  <div class="dw-diffpanel">
    <panel></panel>
    <panel></panel>
  </div>
</template>

<script>
import Panel from "./panel";

export default {
  name: "DWDiffpanel",
  components: {
    Panel
  }
};
</script>

<style lang="stylus">
.dw-diffpanel {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>