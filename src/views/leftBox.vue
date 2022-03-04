<template>
  <div id="leftBox">
    <TitleBox name="环保监测" type="0" nameEn="Environmental Monitoring" />
    <TitleBox name="道路破损" type="1" nameEn="" />
    <TitleBox name="道路积水" type="2" nameEn="" />
    <TitleBox name="道路污迹" type="3" nameEn="" />
    <TitleBox name="车辆灰尘" type="4" nameEn="" />
    <TitleBox name="车辆漏洒" type="5" nameEn="" />
  </div>
</template>

<script>
import TitleBox from '@/components/commons/titleBox'

export default {
  components: {
    TitleBox,
  }
}
</script>

<style lang="scss" scoped>
$box-height: 520px;
$box-width: 100%;
#leftBox {
  
}
</style>
