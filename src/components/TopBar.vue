<template>
  <header class="top-container">
    <div class="top-bar">
      <div class="topbar-nav">
        <ul class="nav-wrap">
          <li class="nav clearfix" v-for="(item,index) in navs">
            <a :href="item.sourceUrl" class="nav-name" target="_blank">{{item.name}}</a>
            <span class="nav-separate" v-show="index!==10">|</span>
          </li>
        </ul>
      </div>
      <div class="top-info">
        <a href="http://order.mi.com/site/login?redirectUrl=http://www.mi.com/index.html">登陆</a><span
        class="info-separate">|</span>
        <a href="https://account.xiaomi.com/pass/register">注册</a><span
        class="info-separate">|</span>
        <a href="http://order.mi.com/site/login?redirectUrl=http://www.mi.com/index.html">消息通知</a>
      </div>
      <div class="top-cart fa cart-arrow-down" @mouseenter="evtCartEnter" @mouseleave="evtCartLeave">
        <div class="top-cart" :class="{'active':cartStatus}">
          <a href="http://static.mi.com/cart/">购物车<span>( 0 )</span></a>
          <i class="fa fa-cart-arrow-down icon-cart"></i>
        </div>
        <transition name="fade">
          <div class="cart" v-show="cartStatus">购物车中还没有商品，赶快选购吧！</div>
        </transition>
      </div>
    </div>
  </header>
</template>

<script type="text/ecmascript-6">
  export default {
    data() {
      return {
        navs: [
          {name: '小米商城', sourceUrl: 'http://www.mi.com/index.html'},
          {name: 'MIUI', sourceUrl: 'http://www.miui.com/'},
          {name: '米聊', sourceUrl: 'http://www.miliao.com/'},
          {name: '游戏', sourceUrl: 'http://game.xiaomi.com/'},
          {name: '多看阅读', sourceUrl: 'http://www.duokan.com/'},
          {name: '云服务', sourceUrl: 'https://i.mi.com/'},
          {name: '金融', sourceUrl: 'https://jr.mi.com/index.html'},
          {name: '米币', sourceUrl: 'https://mibi.mi.com/'},
          {name: '小米商城手机版', sourceUrl: 'http://www.mi.com/c/appdownload/'},
          {name: '问题反馈', sourceUrl: 'http://static.mi.com/feedback/'},
          {name: 'Select Region', sourceUrl: 'http://www.mi.com/index.html'}
        ],
        cartStatus: false,
        timer: null
      }
    },
    methods: {
      evtCartEnter() {
        this.cartStatus = true
        clearInterval(this.timer)
      },
      evtCartLeave() {
        let that = this
        this.timer = setTimeout(() => {
          that.cartStatus = false
        }, 450)
      }
    }
  }
</script>

<style>
  .top-container {
    width: 100%;
    height: 40px;
    background: #333;
  }

  .top-bar {
    position: relative;
    width: 1226px;
    margin: 0 auto;
    z-index: 11;
    font-size: 12px;
  }

  .topbar-nav {
    float: left;
    display: inline-block;
    height: 40px;
    line-height: 40px;
    overflow: hidden;
  }

  .nav-wrap {
    margin: 0;
    padding: 0;
  }

  .nav-wrap .nav {
    display: inline-block;
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
  }

  .nav-wrap .nav:first-child {
    padding-left: 0;
  }

  .nav-name:hover {
    color: #fff;
  }

  .nav-name {
    display: inline-block;
    font-size: 11px;
    color: #b0b0b0;
  }

  .nav-separate {
    display: inline-block;
    color: #424242;
    margin-left: 5px;
  }

  .top-info {
    position: absolute;
    top: 0;
    right: 140px;
    height: 40px;
    line-height: 40px;
  }

  .top-info a {
    color: #b0b0b0;
    margin-left: 5px;
  }

  .top-info a:hover {
    transition: all .5s ease;
    color: #fff;
  }

  .top-info span {
    margin-left: 5px;
    color: #424242;
  }

  .top-cart {
    position: relative;
    top: 0;
    float: right;
    height: 40px;
    width: 120px;
    line-height: 40px;
    background: #424242;
    cursor: pointer;
  }

  .top-cart a {
    display: block;
    width: 100%;
    height: 100%;
    padding-left: 40px;
    color: #0b0b0b;
    box-sizing: border-box;
    text-decoration: none;
  }

  .top-cart .icon-cart {
    position: absolute;
    left: 15px;
    top: 10px;
    color: #b0b0b0;
    font-size: 20px;
  }

  .top-cart a, .icon-cart, span {
    color: #b0b0b0;
  }

  .top-cart .active {
    background: #fff;
  }

  .top-cart .active span {
    color: #ff6700;

  }

  .top-cart .active a {
    color: #ff6700;
  }

  .top-cart .active .icon-cart {
    color: #ff6700;
  }

  .cart {
    position: absolute;
    text-align: center;
    width: 316px;
    height: 99px;
    line-height: 96px;
    top: 40px;
    right: 0;
    box-shadow: 0px 2px 1px 1px rgba(0, 0, 0, 0.15);
    color: #b0b0b0;
    display: block;
    background: #fff;
    z-index: 11;
    overflow: hidden;
  }

  .fade-enter-active, .fade-leave-active {
    transition: all .3s ease;
    height: 96px;
  }

  .fade-enter, .fade-leave-active
    /* .slide-fade-leave-active 在低于 2.1.8 版本中 */
  {
    height: 0;
  }
</style>
