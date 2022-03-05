<template>
  <div id="searchBox">
    <div class="searchInput">
      <span class="searchBtn" @click="showResultFun"></span>
      <input type="text" v-model="val" placeholder="设备或设施名称">
    </div>
    <div v-show="showResult" class="resultBox">
      <ul class="list">
        <li>AIR-DJ001    道路巡检无人机1</li>
        <li>AIR-DJ001    道路巡检无人机2</li>
        <li>AIR-DJ001    道路巡检无人机3</li>
        <li>AIR-DJ001    道路巡检无人机4</li>
        <li>AIR-DJ001    道路巡检无人机5</li>
        <li>AIR-DJ001    道路巡检无人机6</li>
      </ul>
      <div class="pagerBox">
        <div class="before">《</div>
        <ul class="pager">
          <li :class="pager === index ? 'select' : ''" v-for="(item, index) of arr" :key="index" @click="choosePager(index)">{{ item }}</li>
        </ul>
        <div class="after">》</div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: function () {
    return {
      showResult: false,
      val:'',
      arr: [1, 2, 3, 4, 5],
      pager: 1
    };
  },
  methods: {
    showResultFun () {
      this.showResult = !this.showResult;
    },
    choosePager(index){
      this.pager = index
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
#searchBox {
  position: relative;
  .searchInput {
    width: 290px;
    height: 45px;
    line-height: 45px;
    overflow: hidden;
    span, input {
      display: inline-block;
    }
    span, input {
      height: 45px;
      float: left;
    }
    .searchBtn {
      width: 45px;
      background: #5CE1FF url('../assets/search.png') 50% 50% no-repeat;
      background-size: 22px 22px;
      cursor: pointer;
    }
    input {
      width: 245px;
      background: rgba($color: #233345, $alpha: 0.55);
      border: none;
      box-sizing: border-box;
      padding-left: 13px;
      font-size: 18px;
      color: #C5D7EB;
    }
  }
  .resultBox {
    padding: 12px;
    background: rgba($color: #233345, $alpha: 0.55);
    .list {
      li {
        height: 40px;
        line-height: 40px;
        padding-left: 10px;
        border-bottom: 1px solid #C5D7EB;
      }
    }
    .pagerBox {
      overflow: hidden;
      margin-top: 12px;
      div, ul {
        float: left;
      }
      .before {
        float: left;
      }
      div {
        width: 10%;
        text-align: center;
      }
      .after {
        float: right;
      }
      ul {
        overflow: hidden;
        width: 80%;
        li {
          display: inline-block;
          height: 22px;
          text-align: center;
          line-height: 22px;
          font-size: 14px;
          cursor: pointer;
        }
        li {
          float: left;
          width: 20%;
        }
        .select {
          position: relative;
          &::after {
            content: '';
            display: block;
            width: 22px;
            height: 22px;
            background: rgba($color: #5CE1FF, $alpha: .3);
            background-size: 21px 21px;
            position: absolute;
            left: calc(50% - 11px);
            top: 0;
          }
        }
      }
    }
  }
}
</style>
