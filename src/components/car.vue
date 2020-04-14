<!--
 * @Author: liuchuan
 * @Date: 2020-04-14 13:16:00
 * @LastEditTime: 2020-04-14 14:28:49
 * @Description: 
 -->

<template>
  <div class="car">
    <div class="left">
      <img
        :src="
          d.car.carTypeImage ||
            'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586851802345&di=319471f68de155f4eb79179f0e8b27ec&imgtype=0&src=http%3A%2F%2Fwww.juimg.com%2Ftuku%2Fyulantu%2F130708%2F318953-130FQ5160319.jpg'
        "
        alt=""
      />
      <div>{{ d.car.carHeight }}米 {{ d.car.loadingType.desc }}</div>
    </div>
    <!-- <div class="center"> -->
    <line-info :d="lineData"></line-info>
    <!-- <div style="margin: 0 0px 0 60px"> -->
    <price :d="{ price: d.price, count: d.usageCount }"></price>
    <!-- </div>
    </div> -->
    <button class="right">立即用车</button>
  </div>
</template>

<script>
import LineInfo from "./line"
import Price from "./price"
export default {
  name: "car",
  props: {
    d: {
      type: Object,
      default: {}
    }
  },
  components: {
    LineInfo,
    Price
  },
  computed: {
    lineData() {
      const { car, startAddress, endAddress, hoursLength, distance } = this.d
      return {
        v: `${car.carLong}*${car.carWidth}*${car.carHeight}`,
        weight: car.carLoad,
        start: startAddress.city.name + startAddress.district.name,
        end: endAddress.city.name + endAddress.district.name,
        hoursLength,
        distance
      }
    }
  }
}
</script>

<style lang="less" scoped>
.car {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 35px 10px 20px;
  border: 1px solid #999;
  border-radius: 20px;
  .left {
    width: 100px;
    img {
      width: 100%;
      height: auto;
      vertical-align: middle;
      border: 1px solid #ccc;
      border-radius: 10px;
    }
  }
  /* .center {
    flex: 1;
    margin: 0 60px;
    display: flex;
  } */
  .right {
    width: 100px;
    font-size: 18px;
    color: #fff;
    background-color: green;
    padding: 5px 0;
    text-align: center;
    border: none;
    outline: none;
    box-shadow: none;
    border-radius: 5px;
  }
}
</style>
