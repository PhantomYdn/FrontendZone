<template>
  <div class="canvas">
    <CPanel title="Key Partners" row="1/3" column="1" />
    <CPanel title="Key Activities" row="1" column="2" />
    <CPanel title="Value Propositions" row="1/3" column="3" />
    <CPanel title="Customer Relationships" row="1" column="4" />
    <CPanel title="Customer Segments" row="1/3" column="5" />
    <CPanel title="Key Resources" row="2" column="2" />
    <CPanel title="Channels" row="2" column="4" />
    <div class="lowrow">
      <CPanel title="Key Resources" row="1" column="1" />
      <CPanel title="Channels" row="1" column="2" />
    </div>
  </div>
</template>

<script>
import CPanel from "./CPanel";
export default {
  name: "Canvas",
  components: {
    CPanel
  }
  /*props: {
    msg: String
  }*/
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.canvas {
  display: grid;
  grid-template-columns: repeat(5, 2fr);
  grid-auto-rows: minmax(100px, auto);
}

div.lowrow {
  grid-column: 1/6;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
</style>
