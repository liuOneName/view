<!--
 * @Author: liuchuan
 * @Date: 2020-04-14 13:45:36
 * @LastEditTime: 2020-04-14 14:12:00
 * @Description: 
 -->

<template>
  <div class="price-com">
    <div class="price">一口价：¥{{ d.price }}</div>
    <div class="count">累计已发：{{ d.count }}车</div>
  </div>
</template>

<script>
export default {
  props: {
    d: Object
  }
}
</script>

<style lang="less" scoped>
.price-com {
  .count {
    font-size: 14px;
    color: #999;
  }
  .price {
    color: orange;
    font-size: 20px;
    font-weight: bold;
  }
}
</style>
