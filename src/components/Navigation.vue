<template lang="pug">
.navigation
  .header
    #title Connected Academy
    #subtitle A new form of conversation-driven education
    //- br
    //- .button.control-button
      i.fas.fa-play
      |  Watch Video
    #links
      a.link(href="https://github.com/connectedacademy" target="_blank")
        i.fab.fa-lg.fa-github
      a.link(href="https://twitter.com/edjenkins91" target="_blank")
        i.fab.fa-lg.fa-twitter
</template>

<script>
export default {
  name: 'navigation'
}
</script>

<style lang="stylus" scoped>

@import '~stylus/shared'

.navigation
  gradient()
  background-color $color-primary
  height $navigation-height
  text-align center
  .header
    border-box()
    margin 0 auto
    max-width $page-width
    padding 100px 40px
    text-align left
    @media(max-width: 458px)
      padding 80px 20px 40px 20px
      text-align center
    #title
      color white
      font-size 2.4em
      font-weight bold
    #subtitle
      color white
      font-size 1.1em
      font-weight normal
    #links
      position absolute
      top 0
      right 0
      .link
        color white
        display inline-block
        padding 10px
</style>
