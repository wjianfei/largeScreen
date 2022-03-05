<template>
  <div>
    <!-- 年度开工率 -->
    <Echart
      :options="options"
      id="bottomLeftChart"
      height="100%"
      width="100%"
    ></Echart>
  </div>
</template>

<script>
import Echart from "@/common/echart";
export default {
  data() {
    return {
      options: {},
    };
  },
  components: {
    Echart,
  },
  props: {
    cdata: {
      type: Object,
      default: () => ({}),
    },
  },
  watch: {
    cdata: {
      handler(newData) {
        this.options = {
          grid: {
            // left: "3%",
            // right: "4%",
            bottom: "0%",
            containLabel: true,
          },
          // legend: {
          //   show:true
          // },
          xAxis: {
            type: "category",
            data: ["Mon", "Tue", "Wed", "Thu", "Fri"],
          },
          yAxis: {
            type: "value",
          },
          series: [
            {
              data: newData.barData,
              type: "bar",
               barWidth : 8,
              itemStyle:{
                color:'#5CE1FF'
              }
            },
            {
              data: newData.barData,
              type: "bar",
               barWidth : 8,
              itemStyle:{
                color:'#B7EB8F'
              }
            },
          ],
        };
      },
      immediate: true,
      deep: true,
    },
  },
};
</script>
<style scoped>
.chartBox {
  height: 100%;
}
</style>