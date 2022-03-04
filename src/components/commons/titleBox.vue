<template>
  <div class="titleBox">
    <div class="title">
      <span class="icon"></span>
      <span class="name">{{ this.name }}</span>
      <span class="nameEn">{{ this.nameEn }}</span>
    </div>
    <div class="chatBox">
      <div v-if="this.type === '0'"><BottomLeftChart /></div>
    </div>
  </div>
</template>

<script>
import BottomLeftChart from '@/components/echart/bottom/bottomLeftChart'
export default {
  props: {
    name: String,
    type: String,
    nameEn: String
  },
  components: {
    BottomLeftChart
  }
}
</script>

<style lang="scss" scoped>
#leftBox {
  .chatBox {
    height: 180px;
  }
}
</style>
