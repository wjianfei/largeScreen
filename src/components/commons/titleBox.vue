<template>
  <div class="titleBox">
    <div class="title">
      <span class="icon" v-if="this.type === '0'"></span>
      <span :class="'name ' + 'name' + this.type">{{ this.name }}</span>
      <span class="nameEn">{{ this.nameEn }}</span>

      <div v-if="this.type !== '0'" class="line">
        <span class="lineLeft"></span>
        <span class="lineCenter"></span>
        <span class="lineRight"></span>
      </div>
    </div>
    <div class="chatBox">
      <div class="leftChart" v-if="this.type === '0'"><LeftChart1 /></div>
      <div class="leftChart" v-if="this.type === '1'"><LeftChart2 /></div>
      <div class="leftChart" v-if="this.type === '2'"><LeftChart3 /></div>
      <div class="leftChart" v-if="this.type === '3'"><LeftChart4 /></div>
      <div class="leftChart" v-if="this.type === '4'"><LeftChart5 /></div>
      <div class="leftChart" v-if="this.type === '5'"><LeftChart6 /></div>
    </div>
  </div>
</template>

<script>
// import BottomLeftChart from "@/components/echart/bottom/bottomLeftChart";
import LeftChart1 from "@/components/echart/leftChart1";
import LeftChart2 from "@/components/echart/leftChart2";
import LeftChart3 from "@/components/echart/leftChart3";
import LeftChart4 from "@/components/echart/leftChart4";
import LeftChart5 from "@/components/echart/leftChart5";
import LeftChart6 from "@/components/echart/leftChart6";
export default {
  props: {
    name: String,
    type: String,
    nameEn: String,
  },
  components: {
    // BottomLeftChart,
    LeftChart1,
    LeftChart2,
    LeftChart3,
    LeftChart4,
    LeftChart5,
    LeftChart6,
  },
};
</script>

<style lang="scss" scoped>
#leftBox {
  .chatBox {
    height: 130px;
    .leftChart{
      position: relative;
    }
  }
  .name,
  .nameEn {
    margin-left: 10px;
  }
  .name0 {
    margin-left: 30px;
  }
  .title {
    line-height: 20px;
    position: relative;
    font-size: 18px;
    font-family: Yuanti SC;
    font-weight: bold;
    color: #ffffff;
    text-shadow: 0px 0px 5px #5ce1ff;
  }
  .line {
    display: inline-block;
    width: 76%;
    top: -3px;
    position: absolute;
    .lineCenter {
      display: inline-block;
      width: 90%;
      height: 0px;
      border: 1px solid #c5d7eb;
      opacity: 0.3;
    }
    .lineLeft {
      display: inline-block;
      width: 5%;
      border: 1px solid #c5d7eb;
    }
    .lineRight {
      display: inline-block;
      width: 5%;
      border: 1px solid #c5d7eb;
    }
  }

}
</style>
