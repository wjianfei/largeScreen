<template>
  <div id="layerBox">
    <div class="iconList">
      <div :class="item" v-for="(item, index) of iconArr" :key="index" @click="choseLayer(index)"></div>
    </div>
    <div class="detailsBox" :style="'top:' + topPx + 'px'">
      <div v-if="type === 0" class="layerBox">
        <ul>
          <li>图层</li>
          <li>图层</li>
          <li>图层</li>
          <li>图层</li>
        </ul>
      </div>
      <div v-if="type === 1" class="directioBox">方向</div>
      <div v-if="type === 2" class="mapBox">地图</div>
    </div>
  </div>
</template>

<script>

export default {
  data: function () {
    return {
      iconArr: ['layerBtn', 'directionBtn', 'mapBtn'],
      type: '',
      topPx: ''
    };
  },
  methods: {
    choseLayer(index){
      console.log(this.type)
      if (this.type === index) {
        this.type = ''
        this.topPx = '-38'
      } else {
        this.type = index
        if (this.type === 0) {
          this.topPx = '-611'
        }
        if (this.type === 1) {
          this.topPx = '-318'
        }
        if (this.type === 2) {
          this.topPx = '-220'
        }
      }
    }
  },
  mounted () { 
  },
  watch:{
  },
  components: {
  }
}
</script>

<style lang="scss" scoped>
#layerBox {
  position: relative;
  .iconList {
    width: 190px;
    height: 45px;
    box-sizing: border-box;
    background: rgba($color: #233345, $alpha: 0.55);
    overflow: hidden;
    padding: 0 14px;
    &>div {
      float: left;
      width: 54px;
      height: 45px;
      cursor: pointer;
    }
    .layerBtn {
      background: url('../assets/layericon.png') 50% 50% no-repeat;
      background-size: 33px 30px;
    }
    .directionBtn {
      background: url('../assets/directionicon.png') 50% 50% no-repeat;
      background-size: 33px 30px;
    }
    .mapBtn {
      background: url('../assets/mapicon.png') 50% 50% no-repeat;
      background-size: 33px 30px;
    }
  }
  .detailsBox {
    position: absolute;
    top: -38px;
    right: 0px;
    &>div {
      box-sizing: border-box;
      background: #fff;
    }
    .layerBox {
      height: 590px;
      padding: 20px;
      width: 265px;
      background: #fff;
    }
    .directioBox {
      height: 300px;
      width: 200px;
    }
    .mapBox {
      height: 200px;
      width: 200px;
    }
  }
}
</style>
