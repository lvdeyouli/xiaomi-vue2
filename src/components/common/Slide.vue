<template>
  <div class="slide">
    <span class="slide-pre" @click="slidePre">
      <i class="fa fa-chevron-left fa-2x fa-fw icon-chevron-left"></i>
    </span>
    <span class="slide-next" @click="slideNext">
      <i class="fa fa-chevron-right fa-2x fa-fw icon-chevron-right"></i>
    </span>
    <transition-group name="slide" class="move" v-for="(item,index) in banners" v-show="index === curpage" tag="div">
      <a :key="index" :href="item.sourceUrl" target="_blank">
        <img :src="item.imgUrl" alt="">
      </a>
    </transition-group>
    <div class="point">
      <ul>
        <li v-for="(item,index) in banners" class="dot-box" :class="{'dot-box-active':index === curpage}"
            @click="evtmouseClick(index)"></li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      banners: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        Timer: null,
        curpage: 0,
        flag: 0
      }
    },
    mounted() {
      this.autoPlay()
    },
    methods: {
      slideNext() {
        const lastPage = this.banners.length - 1
        if (this.curpage < lastPage) {
          this.curpage += 1
        } else {
          this.curpage = 0
        }
      },
      slidePre() {
        const lastPage = this.banners.length - 1
        if (this.curpage > 0) {
          this.curpage -= 1
        } else {
          this.curpage = lastPage
        }
      },
      autoPlay() {
        clearInterval(this.Timer)
        this.Timer = setInterval(() => {
          this.slideNext()
        }, 5000)
      },
      evtmouseClick(index) {
        this.curpage = index
        clearInterval(this.Timer)
      }
    }
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .slide
    position: relative
    width: 1226px
    height: 460px
    z-index: 0
    .slide-pre
      display: block
      position: absolute
      left: 235px
      top: 50%
      width: 40px
      height: 70px
      margin-top: -35px
      z-index: 10
      cursor: pointer
      &:hover
        background: rgba(0, 0, 0, 0.3)
    .slide-next
      display: block
      position: absolute
      right: 0px
      top: 50%
      width: 40px
      height: 70px
      margin-top: -35px
      z-index: 10
      cursor: pointer
      &:hover
        background: rgba(0, 0, 0, 0.3)
    .move
      position: absolute;
      left: 0;
      top: 0;
      width: 1226px;
      height: 462px;
      transition: all 0.3s;
      img
        width: 100%;
        height: 100%;
    .point
      position: absolute
      width: 150px
      height: 20px
      right: 15px
      bottom: 18px
      cursor: pointer
      .dot-box
        float: left
        width: 6px
        height: 6px
        line-height: 10px
        border-radius: 50%
        border: 2px solid #c0c0c0
        margin-left: 15px
        background: #a0a0a0
        &:hover
          background: #eee
      .dot-box-active
        background: #eee

  .icon-chevron-left, .icon-chevron-right
    position: absolute;
    left: 50%;
    top: 50%;
    width: 30px;
    height: 30px;
    margin-left: -15px;
    margin-top: -15px;
    color: #ecf0f1;

  .slide-enter-active, .slide-leave-active
    transition: all .5s ease;
    opacity: 1
  .slide-enter, .slide-leave-active
    opacity: 0;

  /* 必需 */
  /*.fadeIn-transition {
    transition: all .5s ease;
      opacity: 1;
  }*/

  /* .expand-enter 定义进入的开始状态 */
  /* .expand-leave 定义离开的结束状态 */
  /*.fadeIn-enter, .fadeIn-leave {
    opacity: 0;
  }*/

</style>
