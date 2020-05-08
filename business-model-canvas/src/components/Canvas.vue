<template>
  <div
    class="canvas"
    :style="
      'grid-template-columns: repeat(' +
        layout.columns +
        ', 1fr); grid-auto-rows: minmax(' +
        layout.height +
        ', auto);'
    "
  >
    <CPanel
      v-for="p in layout.panels"
      v-bind:key="p.id"
      :layout="p"
      :data="data[p.id]"
    />
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
      data: {
        partners: ["Drag me", "Drag me too!"],
        activities: [""],
        propositions: [
          "# Hello, Asker and Vitaliy!\n This is just a demo of business model canvas(BMC). **No Design Yet**. It's being developed for BMC, but framework allows to create canvas for other types of canvases.\n\nHow to use:\n\n* Click on required block\n* Enter data as markdown\n* Click in some other place or Ctrl-Enter\n* Drag records in groups and between"
        ],
        relationships: [""],
        segments: [""],
        resources: [""],
        channels: [""],
        cost: [""],
        revenue: [""]
      },
      layout: {
        columns: 10,
        height: "150px",
        panels: [
          {
            id: "partners",
            title: "Key Partners",
            description:
              "Who are our Key Partners?<br/>Who are our key suppliers?<br/>Which Key Resources are we acquiring from partners?<br/>Which Key Activities do partners perform?",
            row: "1/3",
            column: "1/3"
          },
          {
            id: "activities",
            title: "Key Activities",
            description:
              "What Key Activities do our Value Propositions require?<br/>Our Distribution Channels?<br/>Customer Relationships?<br/>Revenue streams?",
            row: "1",
            column: "3/5"
          },
          {
            id: "propositions",
            title: "Value Propositions",
            description:
              "What value do we deliver to the customer?<br/>Which one of our customer’s problems are we helping to solve?<br/>What bundles of products and services are we offering to each Customer Segment?<br/>Which customer needs are we satisfying?",
            row: "1/3",
            column: "5/7"
          },
          {
            id: "relationships",
            title: "Customer Relationships",
            description:
              "What type of relationship does each of our Customer<br/>Segments expect us to establish and maintain with them?<br/>Which ones have we established?<br/>How are they integrated with the rest of our business model?<br/>How costly are they?",
            row: "1",
            column: "7/9"
          },
          {
            id: "segments",
            title: "Customer Segments",
            description:
              "For whom are we creating value?<br/>Who are our most important customers?",
            row: "1/3",
            column: "9/11"
          },
          {
            id: "resources",
            title: "Key Resources",
            description:
              "What Key Resources do our Value Propositions require?<br/>Our Distribution Channels? Customer Relationships?<br/>Revenue Streams?",
            row: "2",
            column: "3/5"
          },
          {
            id: "channels",
            title: "Channels",
            description:
              "Through which Channels do our Customer Segments<br/>want to be reached?<br/>How are we reaching them now?<br/>How are our Channels integrated?<br/>Which ones work best?<br/>Which ones are most cost-efficient?<br/>How are we integrating them with customer routines?",
            row: "2",
            column: "7/9"
          },
          {
            id: "cost",
            title: "Cost Structure",
            description:
              "What are the most important costs inherent in our business model?<br/>Which Key Resources are most expensive?<br/>Which Key Activities are most expensive?",
            row: "3",
            column: "1/6"
          },
          {
            id: "revenue",
            title: "Revenue Streams",
            description:
              "For what value are our customers really willing to pay?<br/>For what do they currently pay?<br/>How are they currently paying?<br/>How would they prefer to pay?<br/>How much does each Revenue Stream contribute to overall revenues?",
            row: "3",
            column: "6/11"
          }
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
}

div.lowrow {
  grid-column: 1/6;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
</style>
