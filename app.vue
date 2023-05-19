<script setup>
import * as Plot from "@observablehq/plot";
import PlotFigure from "./components/PlotFigure.js";
import penguins from "~/assets/penguins.json";

const mark1 = Plot.circle(penguins, Plot.binY({
  x: 'median'
}, {
  x: "Beak Length (mm)",
  y: "Body Mass (g)",
  z: "Beak Depth (mm)",
  fill: "Species",
  sort: { y: "y", reverse: true },
}));
const mark2 = Plot.lineY([0])
</script>
<template>
  <h1>Plot + Vue</h1>
  <PlotFigure
    :options="{
      color: {legend: true},
      insetLeft: 10,
      marginLeft: 69,
      marks: [mark1, mark2, Plot.frame({ anchor: 'bottom'})],
      width: 800
    }"
  />
</template>
