<template>
  <div v-if="Object.keys(goodsInfo).length !== 0" class="base-info">
    <div class="goods-title">{{goodsInfo.title}}</div>
    <div class="goods-price">
      <span class="n-price">{{goodsInfo.newProce}}</span>
      <span class="o-price">{{goodsInfo.oldPrice}}</span>
      <span class="discount">{{goodsInfo.discount}}</span>
    </div>
    <div class="info-other">
      <span>{{goodsInfo.columns[0]}}</span>
      <span>{{goodsInfo.columns[1]}}</span>
      <span>{{goodsInfo.services[goodsInfo.services.length-1].name}}</span>
    </div>
    <div class="info-service">
      <span class="info-service-item" v-for="index in goodsInfo.services.length-1" :key="index">
        <img :src="goodsInfo.services[index-1].icon" alt />
        <span>{{goodsInfo.services[index-1].name}}</span>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailBaseInfo",
  props: {
    goodsInfo: {
      type: Object,
      default() {
        return {};
      }
    }
  }
};
</script>

<style>
.base-info {
  margin-top: 15px;
  padding: 0 8px;
  color: #888;
  border-bottom: 5px solid #f2f5f8;
}
.goods-title {
  color: #222;
}
.goods-price {
  margin-top: 10px;
}
.goods-price .n-price {
  font-size: 24px;
  color: var(--color-high-text);
}
.goods-price .o-price {
  font-size: 13px;
  margin-left: 5px;
  text-decoration: line-through;
}
.goods-price .discount {
  font-size: 12px;
  padding: 2px 5px;
  color: #fff;
  background-color: var(--color-high-text);
  border-radius: 8px;
  margin-left: 10px;
}
.info-other {
  margin-top: 15px;
  line-height: 30px;
  display: flex;
  font-size: 13px;
  border-bottom: 1px solid rgba(100, 100, 100, 0.1);
  justify-content: space-between;
}
.info-service {
  display: flex;
  justify-content: space-between;
  line-height: 60px;
}
.info-service-item img {
  width: 14px;
  height: 14px;
  position: relative;
  top: 2px;
}
.info-service-item span {
  font-size: 13px;
  color: #333;
}
</style>