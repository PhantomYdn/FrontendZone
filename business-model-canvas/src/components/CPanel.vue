<template>
  <div class="cpanel">
    <h5>{{title}}</h5>
    <CEditable :value="'PANEL '+title"/>
  </div>
</template>

<script>
import CEditable from "./CEditable";
export default {
  name: "CPanel",
  props: {
    title: String
  },
  components: {
    CEditable
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
div.cpanel {
  min-height: 100px;
  max-height: 100%;
}
div.cpanel > h5 {
  margin: 0 auto;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
