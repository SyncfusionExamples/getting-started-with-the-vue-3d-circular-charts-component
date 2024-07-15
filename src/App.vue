<template>
  <ejs-circularchart3d tilt="-45" enable-rotation="true"
  title="Berlin 2023 Special Olympics Gold Medals"
  :legendSettings='legendSettings' :tooltip='tooltip' >
      <e-circularchart3d-series-collection>
          <e-circularchart3d-series 
          :dataSource='circularData' xName='country' yName='goldMedals' 
         :dataLabel='dataLabel' radius="70%"  innerRadius='40%'> 
          </e-circularchart3d-series>
      </e-circularchart3d-series-collection>
  </ejs-circularchart3d>
</template>

<script setup>

import { CircularChart3DComponent as EjsCircularchart3d, CircularChart3DSeriesCollectionDirective as ECircularchart3dSeriesCollection, CircularChart3DSeriesDirective as ECircularchart3dSeries,
   PieSeries3D, CircularChartDataLabel3D, CircularChartLegend3D, CircularChartTooltip3D } from "@syncfusion/ej2-vue-charts";
import { provide } from "vue";

const circularData  = [
  { country: 'Canada', goldMedals: 46 },
  { country: 'Hungary', goldMedals: 30 },
  { country: 'Germany', goldMedals: 79 },
  { country: 'Mexico', goldMedals: 13 },
  { country: 'China', goldMedals: 56 },
  { country: 'India', goldMedals: 41 },
  { country: 'Bangladesh', goldMedals: 25 },
  { country: 'United States', goldMedals: 32 },
  { country: 'Belgium', goldMedals: 34 }
  ];
const dataLabel = {
  visible: true,
  name :'country',
  position: 'Outside',
  connectorStyle: {
    length: '50px',
    width: 2
  }
}
const legendSettings = {
  visible: true,
  position:'Bottom'
};
const tooltip= { 
  enable: true,
  format: "<b>${point.x}</b><br>Gold Medals: <b>${point.y}</b>" }
const circularchart3d = [PieSeries3D, CircularChartDataLabel3D, CircularChartLegend3D, 
CircularChartTooltip3D];
provide('circularchart3d', circularchart3d);
</script>