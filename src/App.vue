<template>
  <div id="app">
    <TopImage></TopImage>
    <TopBar></TopBar>
    <TopHeader></TopHeader>
    <TopBanner></TopBanner>
    <TopContainer></TopContainer>
    <GoodsContainer></GoodsContainer>
    <Footer></Footer>
    <playVideo :playconfig="playconfig"></playVideo>
  </div>
</template>

<script>
  import bus from './components/common/store'
  import TopBar from './components/TopBar'
  import TopHeader from './components/TopHeader'
  import TopImage from './components/TopImage'
  import TopBanner from './components/TopBanner.vue'
  import TopContainer from './components/TopContainer.vue'
  import GoodsContainer from './components/GoodsContainer.vue'
  import Footer from './components/page-Footer.vue'
  import playVideo from './components/common/playVideo.vue'
  export default {
    data () {
      return {
        playconfig: {}
      }
    },
    mounted () {
      this.recivePlayVideo()
    },
    methods: {
      recivePlayVideo() {
        bus.$on('play', (opts) => {
          this.playconfig = opts
        })
      }
    },
    components: {
      TopBar, TopHeader, TopImage, TopBanner, TopContainer, GoodsContainer, Footer, playVideo
    }
  }
</script>

<style lang="stylus" ref="stylesheet/stylus">
  @import "assets/css/base.css";
</style>
