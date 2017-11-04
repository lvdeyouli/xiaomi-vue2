<template>
  <div class="smart-goods-top">
    <h3 class="top-title">{{Toptitle}}</h3>
    <ul class="top-subs">
      <li v-for="item in subs" @mouseenter="evtSubEnter(item.key)" :class="{'active':item.key===topSubStatus}">
        {{item.name}}
      </li>
    </ul>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    data() {
      return {
        topSubStatus: this.subs[0].key
      }
    },
    methods: {
      evtSubEnter (value) {
        this.topSubStatus = value
      }
    },
    props: {
      subs: {
        required: true,
        type: Array
      },
      topTitle: {
        required: true,
        type: String
      }
    }
  }
</script>

<style lang="stylus" stylesheet="text/stylus">
  .smart-goods-top
    width: 1226px
    height: 58px
    .top-title
      float: left;
      margin: 0;
      font-size: 22px;
      font-weight: 200;
      height: 58px
      line-height: 58px;
      color: #333;
    .top-subs
      float: right
      display: block
      height: 58px
      line-height: 58px
      li
        float: left
        font-size: 16px
        cursor: pointer
        height: 40px
        margin-left: 20px
        transition: all .5s
        &.active
          color: #ff6700
          border-bottom: 2px solid #ff6700
</style>
