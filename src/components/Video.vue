<template>
  <div class="video-container">
    <div class="header">
      <h2 class="title">{{title}}</h2>
      <a href="//www.mi.com/video/" target="_blank" class="lookall">
        <span class="topsub">查看全部
          <i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
        </span>
      </a>
    </div>
    <div class="video-lists">
      <ul class="lists">
        <li class="list" v-for="item in videos" @click="evtPlay(item)">
          <div class="top-box">
              <img :src="item.imgUrl" alt="">
              <span class="play">
                <i class="fa fa-play"></i>
              </span>
          </div>
          <div class="content">
            <h3 class="video-title">{{item.title}}</h3>
            <p class="desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import bus from './common/store'
  export default {
    data() {
      return {
        title: '视频',
        videos: [{
          videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1ODg5ODA0MA==',
          imgUrl: 'http://i3.mifile.cn/a4/73d67577-cbc7-4bd0-8678-4b1e95f4f4dc',
          title: '红米年度品牌视频',
          desc: '一亿人喜爱你，是一种责任。'
        },
        {
          videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg3NjQ4OA==',
          imgUrl: 'http://i3.mifile.cn/a4/f7e434fb-8ce4-4442-bf78-0d66e409dfc3',
          title: '小米笔记本Air最全介绍视频',
          desc: '带独立显卡的轻薄笔记本'
        },
        {
          videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg4NjY0OA==',
          imgUrl: 'http://i3.mifile.cn/a4/e2df3ad8-4147-44e1-8a54-b6bcafdc6c66',
          title: '小米笔记本Air可靠性测试视频',
          desc: '小米笔记本Air是如何炼成的？'
        },
        {
          videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTU2NDM3NjEzMg==',
          imgUrl: 'http://i3.mifile.cn/a4/T1v3LgBTxv1RXrhCrK.jpg',
          title: '小米Max 绝美外观视频',
          desc: '6.44" 大屏黄金尺寸，看什么都震撼'
        }]
      }
    },
    methods: {
      evtPlay(opts) {
        let videoOpt = {
          status: true,
          title: opts.title,
          videoUrl: opts.videoUrl
        }
        bus.$emit('play', videoOpt)
      }
    }
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .video-container
    width: 1226px
    height: auto
    margin: 0 auto
    .header
      position: relative
      height: 58px
      .title
        float: left
        display: block
        margin: 0
        font-size: 24px
        font-weight: 200
        line-height: 58px
        color: #333
      .topsub
        float: right
        height: 58px
        line-height: 58px
        color: #333
        font-size: 16px
        transition: all .3s
        &:hover
          color: #ff6700
    .video-lists
      position: relative
      width: 1226px
      height: 285px
      .lists
        .list
          float: left
          margin-left: 14px
          width: 296px
          height: 285px
          transition: all 0.3s
          background: #fff
          &:nth-child(1)
            margin-left: 0
          &:hover
            transform:translateY(-3px)
            box-shadow: 5px 5px 20px #ccc
          .top-box
            position: relative
            margin-top: 0
            margin-left: 0
            &:hover
              .play
                border: 2px solid #ff6700
                background: #ff6700
            img
              height: 180px
            .play
              position: absolute
              left: 20px
              bottom: 10px
              width: 32px
              height: 20px
              border: 2px solid #fff
              border-radius: 12px
              background-color: rgba(0,0,0,0.6)
              i
                line-height: 20px
                font-size: 12px
                color: #fff
                text-align: center
                margin-left: 12px
    .content
      position: relative
      .video-title
        margin: 20px 0 0 0
        font-weight: normal
        text-align: center
        font-size: 14px
        cursor: pointer
        &:hover
          color: #ff6700
      .desc
        height: 18px;
        line-height: 18px
        margin-top: 10px
        font-size: 12px;
        text-align: center;
        color: #b0b0b0;
</style>
