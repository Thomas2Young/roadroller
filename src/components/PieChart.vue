<template>
    <div ref="pieChart" class="pie-chart-container" />
  </template>
  
  <script>
  import * as echarts from 'echarts';
  
  export default {
    name: 'PieChart',
    props: {
      // 你可以通过属性传递图表数据和选项
      chartData: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        chartInstance: null
      };
    },
    mounted() {
      this.initChart();
    },
    methods: {
      initChart() {
        this.chartInstance = echarts.init(this.$refs.pieChart);
        this.updateChart();
      },
      updateChart() {
        const option = {
          series: [
            {
              name: '碾压遍数',
              type: 'pie',
              radius: '55%',
              data: this.chartData,
              emphasis: {
                itemStyle: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
              }
            }
          ]
        };
        this.chartInstance.setOption(option);
      }
    },
    watch: {
      // 如果数据变化，更新图表
      chartData: {
        deep: true,
        handler() {
          this.updateChart();
        }
      }
    },
    beforeUnmount() {
      // 在组件销毁前，清理图表实例
      if (this.chartInstance) {
        this.chartInstance.dispose();
      }
    }
  }
  </script>
  
  <style>
  .pie-chart-container {
    width: 100%;
    height: 400px; /* 根据需要调整高度 */
  }
  </style>
  