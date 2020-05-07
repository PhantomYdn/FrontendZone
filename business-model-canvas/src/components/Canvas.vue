<template>
  <div class="canvas" :style="'grid-template-columns: repeat('+layout.columns+', 1fr);'">
    <CPanel v-for="p in layout.panels" v-bind:key="p.id" :layout="p" />
  </div>
</template>

<script>
import CPanel from "./CPanel";
export default {
  name: "Canvas",
  components: {
    CPanel
  },
  data() {
    return {
      layout: {
        columns: 10,
        panels: [
          { id: "partners", title: "Key Partners", row: "1/3", column: "1/3" },
          {
            id: "activities",
            title: "Key Activities",
            row: "1",
            column: "3/5"
          },
          {
            id: "propositions",
            title: "Value Propositions",
            row: "1/3",
            column: "5/7"
          },
          {
            id: "relationships",
            title: "Customer Relationships",
            row: "1",
            column: "7/9"
          },
          {
            id: "segments",
            title: "Customer Segments",
            row: "1/3",
            column: "9/11"
          },
          { id: "resources", title: "Key Resources", row: "2", column: "3/5" },
          { id: "channels", title: "Channels", row: "2", column: "7/9" },
          { id: "cost", title: "Cost Structure", row: "3", column: "1/6" },
          { id: "revenue", title: "Revenue Streams", row: "3", column: "6/11" }
        ]
      }
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.canvas {
  display: grid;
  grid-auto-rows: minmax(100px, auto);
}

div.lowrow {
  grid-column: 1/6;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
</style>
