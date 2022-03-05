<template>
  <div class="leftChart0">
    <div class="box">
      <div class="topBox">
        <div><img src="../../../assets/left01.png" alt="" /></div>
        <div>道路破损</div>
        <div><span class="numText">03</span>处</div>
      </div>
    </div>
    <div class="box">
      <div class="topBox">
        <div><img src="../../../assets/left02.png" alt="" /></div>
        <div>道路积水</div>
        <div><span class="numText">03</span>处</div>
      </div>
    </div>
    <div class="box">
      <div class="topBox">
        <div><img src="../../../assets/left03.png" alt="" /></div>
        <div>道路污迹</div>
        <div><span class="numText">03</span>处</div>
      </div>
    </div>
    <div class="box">
      <div class="topBox">
        <div><img src="../../../assets/left04.png" alt="" /></div>
        <div>车辆灰尘</div>
        <div><span class="numText">03</span>处</div>
      </div>
    </div>
    <div class="box">
      <div class="topBox">
        <div><img src="../../../assets/left05.png" alt="" /></div>
        <div>车辆漏洒</div>
        <div><span class="numText">03</span>处</div>
      </div>
    </div>
  </div>
</template>

<script>
// import Echart from "@/common/echart";
export default {
  data() {
    return {
      options: {},
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
};
</script>
<style scoped  lang="scss">
.leftChart0 {
  .box {
    position: relative;
    margin-left: 1%;
    margin-top: 10px;
    width: 19%;
    height: 103px;
    border: 2px solid rgba(255, 255, 255, 0.9);
    display: inline-block;
    background-color: rgba(255, 255, 255, 0.1);
  }
  .topBox {
    width: 100%;
    height: 100%;
    // opacity: 0.1;
    text-align: center;
    position: absolute;
    img{
        margin: 4px 0 2px 0;
    }
    .numText{
        color: #5CE1FF;
        font-size: 24px;
        display: inline-block;
        margin-top: 2px;
        margin-right: 5px;
    }
  }
  .box::before {
    position: absolute;
    top: -2px;
    bottom: -2px;
    left: 10px;
    width: calc(100% - 20px);
    content: "";
    border-top: 2px solid rgba(75, 100, 120, 0.5);
    border-bottom: 2px solid rgba(75, 100, 120, 0.5);
    z-index: 111;
  }
  .box::after {
    position: absolute;
    top: 10px;
    right: -2px;
    left: -2px;
    height: calc(100% - 20px);
    content: "";
    border-right: 2px solid rgba(75, 100, 120, 0.5);
    border-left: 2px solid rgba(75, 100, 120, 0.5);
    z-index: 111;
  }
}
</style>