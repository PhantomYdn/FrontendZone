<template>
  <div class="cpanel" :style="'grid-row: '+layout.row+'; grid-column: '+layout.column+';'">
    <h4>{{layout.title}}</h4>
    <div class="desc" v-html="layout.description"></div>
    <CEditable v-for="(item, index) in data" :key="index" :value="item" />
  </div>
</template>

<script>
import CEditable from "./CEditable";
export default {
  name: "CPanel",
  props: {
    layout: Object,
    data: Array
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
  display: flex;
  flex-flow: column;
}
div.cpanel > h4 {
  margin: 0 auto;
  white-space: nowrap;
  text-overflow: ellipsis;
}
div.cpanel > div.desc {
  font-style: italic;
  text-align: left;
  font-size: x-small;
}
</style>
