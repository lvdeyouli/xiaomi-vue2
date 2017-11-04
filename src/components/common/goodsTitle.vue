<template>
  <div class="header-wrap">
    <h2 class="title">{{title}}</h2>
  </div>
</template>

<script>
  export default {
    data () {
      return {
      }
    },
    props: {
      title: {
        required: true,
        type: String
      }
    }
  }
</script>

<<style lang="stylus" stylesheet="text/stylus">
  .header-wrap
    position: relative
    .title
      margin: 0
      font-size: 24px
      font-weight: 200
      line-height: 58px
      color: #333
</style>
