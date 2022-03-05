<template>
  <div id="index" ref="appRef">
    <div class="mapBox" v-if="!loading"><img src="../assets/bg.jpeg" alt=""></div>
    <div class="bg">
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div v-else class="host-body">
        <div class="d-flex jc-between titleBox">
          <div class="d-flex jc-center">
            <div class="icon"></div>
            <div class="title">
              <span class="title-text">厂区道路及车辆环保监测</span>
            </div>
          </div>
          <div class="d-flex">
            <div class="timeBox">
              <p class="time">{{ dateDay }}</p>
              <p class="text">{{ dateYear }} {{ dateWeek }}</p>
            </div>
            <div class="weather">
              <p class="day">阴天</p>
              <p class="temperature">10-12℃</p>
            </div>
            <div class="address">
              <div class="addressName">武汉</div>
              <div class="rightBox">
                <p>PM 2.5</p>
                <p>128</p>
              </div>
            </div>
          </div>
        </div>
        <div class="body-box">
          <!-- 左侧栏 -->
          <div class="left-box">
            <LeftBox />
          </div>
          <!-- 搜索 -->
          <div class="search-box">
            <SearchBox /> 
          </div>
        </div>
        <div class="bottom-box">
        </div>
      </div>
      <!-- 右下角图层控件 -->
      <div class="layer-box">
        <LayerBox /> 
      </div>
    </div>
  </div>
</template>

<script>
import drawMixin from "../utils/drawMixin"
import { formatTime } from '../utils/index.js'
import LeftBox from './leftBox'
import SearchBox from './searchBox'
import LayerBox from './layerBox'

export default {
  mixins: [ drawMixin ],
  data() {
    return {
      timing: null,
      loading: true,
      dateDay: null,
      dateYear: null,
      dateWeek: null,
      weekday: ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六']
    }
  },
  components: {
    LeftBox,
    SearchBox,
    LayerBox
  },
  mounted() {
    this.timeFn()
    this.cancelLoading()
  },
  beforeDestroy () {
    clearInterval(this.timing)
  },
  methods: {
    timeFn() {
      this.timing = setInterval(() => {
        this.dateDay = formatTime(new Date(), 'HH: mm: ss')
        this.dateYear = formatTime(new Date(), 'yyyy-MM-dd')
        this.dateWeek = this.weekday[new Date().getDay()]
      }, 1000)
    },
    cancelLoading() {
      setTimeout(() => {
        this.loading = false
      }, 500)
    }
  }
}
</script>

<style lang="scss">
@import '../assets/scss/index.scss';
</style>
