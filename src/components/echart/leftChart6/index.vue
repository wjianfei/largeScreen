<template>
  <div id="leftChart6">
    <dv-capsule-chart :config="config" style="width: 90%; height: 120px;margin-top:20px;" />
  </div>
</template>

<script>
// import Echart from "@/common/echart";
export default {
  data() {
    return {
      config: {
        data: [
          {
            name: "业主车辆",
            value: 167,
          },
          {
            name: "消防车辆",
            value: 67,
          },
        ],
        showValue: true,
        colors: ["#5CE1FF", "#B7EB8F"],
        unit: "辆",
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
  mounted() {},
};
</script>
<style scoped  lang="scss">
#leftChart6 {
  width: 100%;
  height: 150px;
  color: #fff;
}
</style>