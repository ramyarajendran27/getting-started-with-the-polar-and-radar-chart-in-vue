<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :primaryYAxis="chartPrimaryYAxis" 
    :title="chartTitle" :tooltip="chartTooltip">
      <e-series-collection>
        <e-series type="Radar" drawType="Line" :dataSource="chartData" xName="month" 
        yName="temperature" :marker="chartMarker">
        </e-series>
      </e-series-collection>
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, PolarSeries, LineSeries, Category, Tooltip, ColumnSeries, 
RadarSeries } from '@syncfusion/ej2-vue-charts';

Vue.use(ChartPlugin);

export default {
  provide : {
    chart : [PolarSeries, LineSeries, Category, Tooltip, ColumnSeries, RadarSeries]
  },
  data() {
    return {
      chartTooltip : {
        enable : true
      },
      chartMarker : {
        visible : true,
        height : 7,
        width : 7
      },
      chartTitle : 'Weather Statistics',
      chartPrimaryYAxis : {
        minimum : -25,
        maximum : 25,
        interval : 10,
        labelFormat : '{value}°C' 
      },
      chartPrimaryXAxis : {
        valueType : 'Category',
        labelPlacement : 'OnTicks',
        startAngle : 45,
        coefficient : 70
      },
      chartData : [
         { month :  "Jan", temperature :  -7.1 },
         { month :  "Feb", temperature :  -3.7 },
         { month :  "Mar", temperature :  0.8  },
         { month :  "Apr", temperature :  6.3 },
         { month :  "May", temperature :  13.3 },
         { month :  "Jun", temperature :  18.0 },
         { month :  "Jul", temperature :  19.8 },
         { month :  "Aug", temperature :  18.1 },
         { month :  "Sep", temperature :  13.1 },
         { month :  "Oct", temperature :  4.1 },
         { month :  "Nov", temperature :  -3.8 },
         { month :  "Dec", temperature :  -6.8 }
      ]

    };
  }
 
}
</script>

<style>
</style>
