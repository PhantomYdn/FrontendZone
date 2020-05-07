<template>
  <div class="canvas">
    <CPanel title="Key Partners" row="1/3" column="1/3" />
    <CPanel title="Key Activities" row="1" column="3/5" />
    <CPanel title="Value Propositions" row="1/3" column="5/7" />
    <CPanel title="Customer Relationships" row="1" column="7/9" />
    <CPanel title="Customer Segments" row="1/3" column="9/11" />
    <CPanel title="Key Resources" row="2" column="3/5" />
    <CPanel title="Channels" row="2" column="7/9" />
    <CPanel title="Key Resources" row="3" column="1/6" />
    <CPanel title="Channels" row="3" column="6/11" />
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
  grid-template-columns: repeat(10, 1fr);
  grid-auto-rows: minmax(100px, auto);
}

div.lowrow {
  grid-column: 1/6;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
</style>
