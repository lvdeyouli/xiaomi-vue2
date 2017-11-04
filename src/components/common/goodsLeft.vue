<template>
  <div class="Goods-left">
    <ul class="goods-left">
      <li class="good-left" v-for="item in leftGoods">
        <a :href="item.sourceUrl"><img :src="item.imgUrl" alt="" class="pic"></a>
      </li>
    </ul>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      leftGoods: {
        required: true,
        type: Array
      }
    },
    data() {
      return {}
    },
    methods: {}
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .Goods-left
    float: left
    width: 234px
    height: 614px
    transition: all .3s
    .goods-left
      position: relative
      .good-left
        height: 314px
        width: 234px
        .pic
          width: 235px
          height: 300px
          transition: all .3s
          &:hover
            transform: translateY(-1px)
            box-shadow: 5px 5px 20px #ccc
</style>
