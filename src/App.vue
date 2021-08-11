<template>
  <ejs-chart>
      <e-series-collection>
          <e-series :dataSource='seriesData' type='Line' xName='x' yName='y'> </e-series>
      </e-series-collection>
  </ejs-chart>
</template>

<script>
import { ChartComponent, SeriesCollectionDirective, SeriesDirective, LineSeries, Legend, Chart } from "@syncfusion/ej2-vue-charts";
import { createApp } from "vue";

Chart.Inject(LineSeries, Legend);

const app = createApp({
  // Displays "Hello, World" initially, changes based on input
  template: '<app></app>'
}); 

// Register the `hello` component
var itemVue = app.component('itemTemplate', {
  data: () => ({}),
});  
 
export default {
  name: "App",
  components: {
    'ejs-chart' : ChartComponent,
    'e-series-collection' : SeriesCollectionDirective,
    'e-series' : SeriesDirective
  },
  data() {
    return {
      seriesData: [
        { x: 10, y: 21 },
        { x: 20, y: 24 },
        { x: 30, y: 36 },
        { x: 40, y: 38 },
        { x: 50, y: 54 },
        { x: 60, y: 57 },
        { x: 70, y: 70 }
      ],
      itemTemplate:  function() {
        return { template: itemVue };
      }
    };
  },
};
</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";

button {
  margin: 25px 5px 20px 20px;
}
</style>
