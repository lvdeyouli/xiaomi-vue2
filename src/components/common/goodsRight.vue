<template>
  <div class="smart-goods-right">
    <ul class="currgoods">
      <template v-for="(item, index) in currGoods" v-if="index < currGoods.length - 1">
        <li class="currgood">
          <span class="discount-label" :class="item.discountType">{{item.discount}}</span>
          <a :href="item.sourceUrl" target="_blank">
            <img :src="item.imgUrl" alt="">
            <h3 class="goods-title">{{item.title}}</h3>
          </a>
          <p class="desc">{{item.desc}}</p>
          <p class="price">{{item.price}}元<span v-if="item.discountType==='discount'">{{item.oldPrice}}</span></p>
          <p class="heat">{{item.heat}}人评价</p>
          <div class="review" v-show="item.reviewStatus">
            <div class="review-desc">{{item.reviewDesc}}</div>
            <div class="review-author">来自于{{item.reviewAuthor}}的评价</div>
          </div>
        </li>
      </template>
      <ul class="lastgoods">
        <template v-if="lastGoods">
          <li class="lastgood">
            <a :href="lastGoods.sourceUrl">
              <div class="desc">
                <h3 class="last-title">{{lastGoods.title}}</h3>
                <p class="last-price">{{lastGoods.price}}元</p>
              </div>
              <img :src="lastGoods.imgUrl" alt="">
            </a>
          </li>
          <li class="more">
            <a :href="lastGoods.moreUrl">
              <div class="text">
                <h3 class="viewmore">浏览更多</h3>
                <p class="hot">热门</p>
              </div>
              <i class="fa fa-arrow-circle-right fa-4x icon-arrow"></i>
            </a>
          </li>
        </template>
      </ul>
    </ul>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      currGoods: {
        required: true,
        type: Array
      }
    },
    data() {
      return {}
    },
    methods: {},
    computed: {
      lastGoods() {
        if (this.currGoods && this.currGoods.length - 1 > 0) {
          return this.currGoods[this.currGoods.length - 1]
        } else {
          return null
        }
      }
    }
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .smart-goods-right
    float: right
    height: 614px
    width: 992px
    .currgoods
      display: flex;
      flex-flow: row wrap;
      justify-content: flex-start;
      width: 100%;
      height: 100%;
      .currgood
        position: relative
        float: left
        margin: 0 0 14px 14px
        padding: 20px 0
        width: 234px
        height: 260px
        background: #fff
        transition: all 0.3s
        img
          display: block
          width: 160px
          height: 160px
          margin: 0 auto
        &:hover
          transform: translateY(-1px)
          box-shadow: 5px 5px 20px #ccc
          .review
            height: 76px
            opacity: 1
        .discount-label
          position: absolute
          top: 0
          width: 64px
          left: 50%
          margin-left: -32px
          height: 20px
          line-height: 20px
          font-size: 12px
          color: #fff
          text-align: center
          z-index: 4
        .free
          background: #ffac13
        .new
          background: #83c44e
        .discount
          background: #e53935
        .goods-title
          font-size: 14px
          font-weight: normal
          text-align: center
        .heat
          margin: 0 10px 10px
          font-size: 12px
          text-align: center
          height: 18px
          text-overflow: ellipsis
          overflow: hidden
          white-space: nowrap
          color: #b0b0b0
        .price
          font-size: 14px
          color: #ff6700
          text-align: center
        .oldprice
          font-size: 14px
          color: #b0b0b0
        .review
          position: absolute;
          left: 0;
          bottom: 0;
          width: 234px;
          font-size: 12px;
          height: 0;
          line-height: 18px;
          overflow: hidden;
          box-sizing: border-box;
          background: #ff6700;
          opacity: 0;
          transition: all 0.3s;
          .review-desc
            display: block
            text-align: center
            margin: 8px 30px
            color: #fff
          .review-author
            display: block
            text-align: center
            margin: 0px 45px
            color: #fff
      .lastgoods
        position: relative
        margin: 0 0 14px 14px
        width: 234px
        height: 260px
        transition: all 0.3s
        .lastgood
          position: absolute
          top: 0
          width: 234px
          height: 143px
          background: #fff
          transition: all 0.3s
          &:hover
            transform: translateY(-1px)
            box-shadow: 5px 5px 20px #ccc
          .desc
            width: 80px
            height: 80px
            float: left
            margin: 30px 0 30px 30px
            .last-title
              font-size: 14px
              font-weight: normal
              text-align: center
              text-overflow: ellipsis
              white-space: nowrap
              overflow: hidden
            .last-price
              font-size: 14px
              color: #ff6700
              margin-left: 25px
          img
            margin-top: 25px
            margin-right: 30px
            float: right
            width: 80px
            height: 80px
        .more
          position: absolute
          width: 234px
          height: 143px
          background: #fff
          margin-top: 158px
          .text
            width: 80px
            height: 100%
            float: left
            margin: 30px 0 30px 30px
            .viewmore
              font-size: 14px
              font-weight: normal
              text-align: center
            .hot
              color: #ff6700
              font-size: 14px
              text-align: center
          .icon-arrow
            color: #ff6700
            margin-top: 30px
            margin-right: 15px
            float: right
            width: 80px
            height: 80px
          &:hover
            transform: translateY(-1px)
            box-shadow: 5px 5px 20px #ccc
</style>
