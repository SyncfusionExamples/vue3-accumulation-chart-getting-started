<template>
    <ejs-accumulationchart :legendSettings="legendSettings" :tooltip="tooltip">
        <e-accumulation-series-collection>
            <e-accumulation-series :dataSource='data' xName='x' yName='y' innerRadius="20%"> </e-accumulation-series>
        </e-accumulation-series-collection>
    </ejs-accumulationchart>
</template>

<script>
import { AccumulationChartComponent, AccumulationSeriesCollectionDirective, AccumulationSeriesDirective, AccumulationLegend,
PieSeries, AccumulationTooltip } from "@syncfusion/ej2-vue-charts";

export default {
    name: "App",
    components: {
    "ejs-accumulationchart": AccumulationChartComponent,
    "e-accumulation-series-collection": AccumulationSeriesCollectionDirective,
    "e-accumulation-series":  AccumulationSeriesDirective
  },
  data() {
    return {
      data: [
        { x: 'Argentina', y: 505370 },
        { x: 'Belgium', y: 551500 },
        { x: 'Cuba', y: 312685 },
        { x: 'Dominican Republic', y: 350000 },
        { x: 'Egypt', y: 301000 },
        { x: 'Kazakhstan', y: 300000 },
        { x: 'Somalia', y: 357022 }
     ],
     legendSettings: { visible: true },
     tooltip: {
        enable: true
     },
    };
  },
  provide: {
    accumulationchart: [AccumulationLegend, PieSeries, AccumulationTooltip]
  },
};
</script>