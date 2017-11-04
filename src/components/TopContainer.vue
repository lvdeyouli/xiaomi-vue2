<template>
  <div class="center-container">
    <div class="con-box-left">
      <ul class="channels">
        <li class="channel">
          <a href="http://www.mi.com/compare/" target="_blank">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p class="channel-txt">
              选购手机
            </p>
          </a>
        </li>
        <div class="line-vertical">
        </div>
        <li class="channel">
          <a href="http://qiye.mi.com/" target="_blank">
            <i class="fa fa-gift fa-fw sub-icon"></i>
            <p class="channel-txt">
              企业团购
            </p>
          </a>
        </li>
        <div class="line-vertical">
        </div>
        <li class="channel">
          <a href="http://item.mi.com/re" target="_blank">
            <i class="fa fa-refresh fa-fw sub-icon"></i>
            <p class="channel-txt">
              官翻产品
            </p>
          </a>
        </li>
        <div class="line-horizontal">
        </div>
        <div class="line-horizontal">
        </div>
        <div class="line-horizontal">
        </div>
        <li class="channel">
          <a href="http://huanxin.mi.com/product/list" target="_blank">
            <i class="fa fa-credit-card fa-fw sub-icon"></i>
            <p class="channel-txt">小米移动</p>
          </a>
        </li>
        <div class="line-vertical">
        </div>
        <li class="channel">
          <a href="http://huanxin.mi.com/product/list" target="_blank">
            <i class="fa fa-recycle fa-fw sub-icon"></i>
            <p class="channel-txt">
              以旧换新
            </p>
          </a>
        </li>
        <div class="line-vertical">
        </div>
        <li class="channel">
          <a href="http://recharge.10046.mi.com/" target="_blank">
            <i class="fa fa-credit-card-alt fa-fw sub-icon"></i>
            <p class="channel-txt">
              话费充值
            </p>
          </a>
        </li>
      </ul>
    </div>
    <div class="con-box-right">
      <ul class="block">
        <li>
          <a href="http://hd.mi.com/y/08191p/index.html" class="block-list1" target="_blank">
            <img src="http://i3.mifile.cn/a4/1327d707-4f67-4c36-8ae5-3d7704c989eb" alt=""/>
          </a>
        </li>
        <li>
          <a href="http://item.mi.com/buyphone/redmipro/" class="block-list2" target="_blank">
            <img src="http://i3.mifile.cn/a4/c202123c-4197-4666-9793-2f1e156ab23a" alt=""/>
          </a>
        </li>
        <li>
          <a href="http://item.mi.com/static/buymipad" class="block-list3" target="_blank">
            <img src="http://i3.mifile.cn/a4/216f7f38-66ee-4c1b-8409-8d77cb64d386" alt=""/>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    data() {
      return {}
    },
    methods: {}
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .center-container
    position: relative
    width: 1226px
    height: 170px
    margin: 15px auto 25px
    z-index: 11
    .con-box-left
      float: left
      width: 235px
      height: 170px
      cursor: pointer
      background: #5f5750;
      .channels
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-start;
        align-items: flex-start;
        list-style: none;
        margin: 0;
        padding: 3px;
        .channel
          width: 75px
          height: 82px
          float: left
          transition: all .3s
          &:hover
            .sub-icon, .channel-txt
              color: #fff
          .sub-icon
            width: 75px
            height: 24px
            font-size: 20px
            margin-top: 20px
            color: rgba(255,255,255,0.7);
          .channel-txt
            position: relative
            padding-left: 13px
            bottom: 6px
            font-size: 12px
            color: rgba(255,255,255,0.7);
        .line-vertical
          width: 1px;
          height: 60px;
          margin-top: 10px;
          background: rgba(255,255,255,0.1);
        .line-horizontal
          width: 60px;
          height: 1px;
          margin: 0 8px;
          background: rgba(255,255,255,0.1);
    .con-box-right
      float: right
      width: 991px
      height: 170px
      .block
        position: relative
        height: 170px
        width: 990px
        line-height: 170px
        li
          width: 317px
          height: 170px
          float: left
          margin-left: 13px
          cursor: pointer
          transition: all .3s
          &:hover
            box-shadow: 0 5px 30px #bbb
          img
            display: block
            width: 316px
            height: 170px
</style>
