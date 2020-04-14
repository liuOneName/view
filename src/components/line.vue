<!--
 * @Author: liuchuan
 * @Date: 2020-04-14 13:23:25
 * @LastEditTime: 2020-04-14 14:10:21
 * @Description: 
 -->

<template>
  <div class="line">
    <div class="line-left">
      <div class="start">{{ d.start }}</div>
      <div class="">载货体积：{{ d.v }}</div>
    </div>
    <div class="line-center">
      <div>{{ d.hoursLength }}h</div>
      <div class="arrow"></div>
      <div>{{ d.distance }}km</div>
    </div>
    <div class="line-right">
      <div class="start">{{ d.end }}</div>
      <div class="">载货体积：{{ d.weight }}吨</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "line",
  props: {
    d: Object
  }
}
</script>

<style lang="less" scoped>
.line {
  display: flex;
  align-items: flex-start;
  flex: 1;
  &-center {
    width: 100px;
    text-align: center;
    font-size: 13px;
    line-height: 1;
    .arrow {
      height: 4px;
      background-color: #000;
      width: 25px;
      display: inline-block;
      position: relative;
      &::after {
        content: "";
        position: absolute;
        border-left: 10px solid #000;
        border-top: 6px solid transparent;
        border-bottom: 6px solid transparent;
        margin-top: -4px;
        right: -8px;
      }
    }
  }
  &-left {
    text-align: right;
  }
  &-left,
  &-right {
    flex: 1;
    font-size: 14px;
    .start {
      font-size: 20px;
      font-weight: bold;
    }
  }
}
</style>
