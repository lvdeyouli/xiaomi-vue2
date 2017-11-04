<template>
  <div class="play-video">
    <div class="mask" v-show="maskstatus">
      <transition name="slideIn">
        <div class="video-content" v-show="videostatus">
          <div class="header">
            <h3 class="title">{{playconfig.title}}</h3>
            <div class="cancel-button" @click="evtcancel">
              <i class="cancel-btn fa fa-times"></i>
            </div>
          </div>
          <div class="playwindow">
            <iframe width="880" height="536" :src="playconfig.videoUrl" frameborder="0" allowfullscreen=""></iframe>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      playconfig: {
        required: true,
        type: Object
      }
    },
    data() {
      return {
        maskstatus: false
      }
    },
    watch: {
      videostatus(newVal, oldVal) {
        const that = this
        if (!newVal) {
          setTimeout(() => {
            that.maskstatus = that.videostatus
          }, 500)
        }
        that.maskstatus = that.videostatus
      }
    },
    methods: {
      evtcancel() {
        this.playconfig.status = false
        this.playconfig.videoUrl = ''
      }
    },
    computed: {
      videostatus() {
        return this.playconfig.status
      }
    }
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .mask
    position: fixed
    left: 0
    top: 0
    width: 100%
    height: 100%
    background: rgba(0, 0, 0, 0.5)
    z-index: 12
    .video-content
      position: absolute
      width: 880px
      height: 596px
      margin-left: -440px
      left: 50%
      top: 50%
      margin-top: -283px
      background: #fff
      .header
        padding: 16px 16px
        background: #f5f5f5
        .title
          font-weight: 400
          font-size: 19px
          line-height: 36px
          height: 30px
          color: #424242
          margin: 0
        .cancel-button
          position: absolute
          top: 17px
          right: 10px
          width: 30px
          height: 30px
          border-radius: 50%
          color: #b0b0b0
          font-size: 25px
          text-align: center
          transition: all .2s
          &:hover
            background: red
            color: #fff
      .play-window
        width: 880px
        height: 536px
        iframe
          height: 880px
          width: 536px
          margin: 0

  .slideIn-enter-active, .slideIn-leave-active
    transition: all .3s ease-out
    transform: translateY(30%)

  .slideIn-enter, .slideIn-leave
    transform: translateY(-100%)
</style>
