<template>
  <table class="canvas">
    <tbody>
      <tr>
        <td colspan="2" rowspan="2" style="width:20%">
          <CPanel title="Key Partners"/>
        </td>
        <td colspan="2" style="width:20%">
          <CPanel title="Key Activities"/>
        </td>
        <td colspan="2" rowspan="2" style="width:20%">
          <CPanel title="Value Propositions"/>
        </td>
        <td colspan="2" style="width:20%">
          <CPanel title="Customer Relationships"/>
        </td>
        <td colspan="2" rowspan="2" style="width:20%">
          <CPanel title="Customer Segments"/>
        </td>
      </tr>
      <tr>
        <td colspan="2">
          <CPanel title="Key Resources"/>
        </td>
        <td colspan="2">
          <CPanel title="Channels"/>
        </td>
      </tr>
      <tr>
        <td colspan="5">
          <CPanel title="Key Resources"/>
        </td>
        <td colspan="5">
          <CPanel title="Channels"/>
        </td>
      </tr>
    </tbody>
  </table>
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
<style>
table.canvas {
  table-layout: fixed;
}

table.canvas > tbody > tr > td {
  border: solid black 1px;
  vertical-align: top;
  height: 1px;
}
</style>
