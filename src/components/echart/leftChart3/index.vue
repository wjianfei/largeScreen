<template>
  <div id="leftChart3"></div>
</template>

<script>
// import Echart from "@/common/echart";
export default {
  data() {
    return {
      options: {
        grid: {
          left: "3%",
          right: "4%",
          bottom: "2%",
          containLabel: true,
        },
        legend: {},
        xAxis: {
          type: "category",
          data: ["10:20", "11:20", "12:20", "13:20", "14:20", "15:20"],
          axisLine: {
            lineStyle: {
              color: "#fff",
            },
          },
          axisTick: {
            show: false,
          },
          axisLabel: {
            show: true,
            textStyle: {
              color: "#ffffff",
            },
          },
        },
        yAxis: {
          type: "value",
          name: "单位：m2",
          nameTextStyle: {
            color: "#fff",
          },
          axisTick: {
            show: false,
          },
          axisLine: { show: false },
          splitLine: {
            show: true,
            lineStyle: {
              type: "dashed",
              color: "#fff",
              opacity: 0.5,
            },
          },
          axisLabel: {
            show: true,
            textStyle: {
              color: "#ffffff",
            },
          },
        },
        series: [
          {
            data: [100, 300, 500, 400, 200, 800],
            type: "line",
            areaStyle: {},
            barWidth: 8,
            itemStyle: {
              color: "#5CE1FF",
            },
          },
          {
            data: [400, 200, 600, 500, 190, 100],
            type: "line",
            areaStyle: {},
            barWidth: 8,
            itemStyle: {
              color: "#B7EB8F",
            },
          },
        ],
      },
    };
  },
  components: {
    // Echart,
  },
  props: {
    cdata: {
      type: Object,
    },
  },
  watch: {},
  mounted() {
    var chartBar = this.$echarts.init(document.getElementById("leftChart3"));
    chartBar.setOption(this.options);
  },
};
</script>
<style scoped  lang="scss">
#leftChart3 {
  width: 100%;
  height: 150px;
  color: #fff;
  position: absolute;
  top: -25px;
}
</style>