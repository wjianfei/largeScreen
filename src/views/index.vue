<template>
  <div id="index" ref="appRef">
    <div class="bg">
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div v-else class="host-body">
        <div class="d-flex jc-between">
          <div class="d-flex jc-center">
            <div class="icon">img</div>
          </div>
          <div class="d-flex jc-center">
            <div class="title">
              <span class="title-text">武钢厂区道路及车辆环保监测</span>
            </div>
          </div>
          <div class="d-flex">
              <span class="text">{{ dateYear }} {{ dateWeek }} {{ dateDay }}</span>
          </div>
        </div>

        <!-- 第二行 -->
        <div class="d-flex jc-between px-2">
        </div>
        <div class="body-box">
          <!-- 第三行数据 -->
          <div class="content-box">
          </div>
          <!-- 第四行数据 -->
          <div class="bototm-box">
            <dv-border-box-13>
              <bottomLeft />
            </dv-border-box-13>
            <dv-border-box-12>
              <bottomRight />
            </dv-border-box-12>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import drawMixin from "../utils/drawMixin";
import { formatTime } from '../utils/index.js'
// import centerLeft1 from './centerLeft1'
// import centerLeft2 from './centerLeft2'
// import centerRight1 from './centerRight1'
// import centerRight2 from './centerRight2'
// import center from './center'
import bottomLeft from './bottomLeft'
import bottomRight from './bottomRight'

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
    bottomLeft,
    bottomRight
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
