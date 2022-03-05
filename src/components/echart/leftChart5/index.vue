<template>
  <div id="leftChart5">
    <dv-scroll-board
      :config="config"
      style="width: 90%; height: 80%; margin: 5px auto"
    />
  </div>
</template>

<script>
// import Echart from "@/common/echart";
export default {
  data() {
    return {
      config: {
        header: ["地点", "状况", "时间"],
        data: [
          ["行1列1", "行1列2", "行1列3"],
          ["行2列1", "行2列2", "行2列3"],
          ["行3列1", "行3列2", "行3列3"],
          ["行4列1", "行4列2", "行4列3"],
          ["行5列1", "行5列2", "行5列3"],
          ["行6列1", "行6列2", "行6列3"],
          ["行7列1", "行7列2", "行7列3"],
          ["行8列1", "行8列2", "行8列3"],
          ["行9列1", "行9列2", "行9列3"],
          ["行10列1", "行10列2", "行10列3"],
        ],
        index: true,
        columnWidth: [50],
        align: ["center"],
        rowNum: 3,
        indexHeader:'序号',
        headerBGC: 'rgba(1,1,1,0)',
        oddRowBGC:'rgba(35, 51, 69, 0.3)',
        evenRowBGC:'rgba(35, 51, 69, 0.5)',
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
    // var chartBar = this.$echarts.init(document.getElementById("leftChart5"));
    // chartBar.setOption(this.options);
  },
};
</script>
<style scoped  lang="scss">
#leftChart5 {
  width: 100%;
  height: 150px;
  color: #C5D7EB;
}
</style>