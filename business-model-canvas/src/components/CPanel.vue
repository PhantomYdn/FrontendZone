<template>
  <div class="cpanel" :style="'grid-row: '+layout.row+'; grid-column: '+layout.column+';'">
    <h5>{{layout.title}}</h5>
    <CEditable :value="'PANEL '+layout.title" />
  </div>
</template>

<script>
import CEditable from "./CEditable";
export default {
  name: "CPanel",
  props: {
    layout: Object
  },
  components: {
    CEditable
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
div.cpanel {
  width: 100%;
  height: 100%;
  border: solid 1px red;
}
div.cpanel > h5 {
  margin: 0 auto;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
