<template>
  <div class="dw-panel">
    <pre>import 'well done'</pre>
  </div>
</template>

<script>
export default {
  name: "DWPanel"
};
</script>

<style lang="stylus">
.dw-panel {
  color: red;
  font-weight: bold;
  min-height: 480px;
  margin: 10px;
  flex-basis: 400px;
  border-right: 2px dashed red;

  &:nth-child(2) {
    border-right: none;
  }
}
</style>