<template>
  <div class="goods-container">
    <Smart></Smart>
    <Goods-match></Goods-match>
    <Accessouries></Accessouries>
    <Around></Around>
    <Recommend></Recommend>
    <Hot-goods></Hot-goods>
    <Goods-content></Goods-content>
    <Video></Video>
  </div>
</template>

<script type="text/ecmascript-6">
  import Smart from './Smart.vue'
  import GoodsMatch from './GoodsMatch.vue'
  import Accessouries from './Accessouries.vue'
  import Around from './Around.vue'
  import Recommend from './Recommend.vue'
  import HotGoods from './HotGoods.vue'
  import GoodsContent from './GoodsContent.vue'
  import Video from './Video.vue'

  export default {
    data() {
      return {}
    },
    methods: {},
    components: {
      Smart, GoodsMatch, Accessouries, Around, Recommend, HotGoods, GoodsContent, Video
    }
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .goods-container
    width: 100%
    height: auto;
    background: #f5f5f5
    padding-bottom: 60px
</style>
