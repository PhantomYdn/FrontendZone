<template>
  <div
    class="cpanel"
    :style="'grid-row: ' + layout.row + '; grid-column: ' + layout.column + ';'"
  >
    <h4>{{ layout.title }}</h4>
    <div class="desc" v-html="layout.description"></div>
    <draggable
      tag="div"
      class="group"
      dragClass="dragging"
      :list="data"
      handle="div.drag"
      group="editables"
      forceFallback="true"
    >
      <CEditable
        v-for="(item, index) in data"
        :key="item"
        :value="item"
        :index="index"
        v-on:changeValue="changeValue"
      />
    </draggable>
  </div>
</template>

<script>
import CEditable from "./CEditable";
import draggable from "vuedraggable";
export default {
  name: "CPanel",
  props: {
    layout: Object,
    data: Array
  },
  components: {
    draggable,
    CEditable
  },
  methods: {
    changeValue: function(index, newValue) {
      this.data[index] = newValue;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
div.cpanel {
  width: 100%;
  height: 100%;
  border: solid 1px rgb(177, 143, 185);
  background: rgb(208, 169, 218);
}

div.cpanel,
div.cpanel > div.group {
  display: flex;
  flex-flow: column;
  height: 100%;
}

div.cpanel:hover {
  background: rgb(196, 158, 204);
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
  padding: 3px 2em;
}
</style>
