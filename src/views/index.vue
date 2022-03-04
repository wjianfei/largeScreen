<template>
  <div id="index" ref="appRef">
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
              <span class="text">{{ dateYear }} {{ dateWeek }} {{ dateDay }}</span>
          </div>
        </div>
        <div class="body-box">
          <!-- 左侧栏 -->
          <div class="left-box">
            <LeftBox />
          </div>
          <!-- 搜索 -->
          <div class="search-box">
          </div>
          <!-- 右下角图层控件 -->
          <div class="search-box">
          </div>
        </div>
        <div class="bottom-box">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import drawMixin from "../utils/drawMixin"
import { formatTime } from '../utils/index.js'
import LeftBox from './leftBox'

export default {
  mixins: [ drawMixin ],
  data() {
    return {
      timing: null,
      loading: true,
      dateDay: null,
      dateYear: null,
      dateWeek: null,
      weekday: ['周日', '周一', '周二', '周三', '周四', '周五', '周六']
    }
  },
  components: {
    // centerLeft1,
    // centerLeft2,
    // centerRight1,
    // centerRight2,
    // center,
    LeftBox
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
