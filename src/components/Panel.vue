<template lang="pug">
  .panel.split
    .simple
      .col
        .content
          .title.blue-text
            slot(name="title")
          .body.blue-text
            slot(name="body")
          slot(name="content")
          .button.info-button(v-if="canToggle" @click="togglePanel") {{ expanded ? 'Collapse' : 'Read More' }}
      slot(name="image")
      .clearfix
    .detail(v-show="expanded")
      .content
        slot(name="detail")
</template>

<script>
export default {
  name: 'Panel',
  props: ['canToggle'],
  data () {
    return {
      expanded: false
    }
  },
  methods: {
    togglePanel () {
      this.expanded = !this.expanded
    }
  }
}
</script>

<style lang="stylus" scoped>

@import '~stylus/shared'

.panel
  box-sizing()
  // box-shadow(0 0 5px 5px alpha(black, 0.03))
  border $color-border 1px solid
  background-color white
  margin-left 20px
  margin-right 20px
  margin-bottom 60px
  min-height 100px
  position relative
  z-index 10
  perspective 1600px
  &:hover .image
    transform rotateY(-30deg) translateX(-30px)
  &:hover .phone
    // transform translateY(-30px)
    &.bottom
      top -20%
    &.top
      bottom -20%
  @media(max-width: 768px)
    margin-bottom 20px
  &:first-child
    margin-top -20px
  &:last-child
    margin-bottom -20px
  .simple
    position relative
  .pink-text
    color $color-pink
  .blue-text
    color $color-dark-blue
  .title
    font-size 1.6em
    font-weight bold
    margin-bottom 10px
  .body
    font-size 1.2em
  .button
    margin-top 20px
  &.split
    &:before
      pinned()
      content ''
      left 70%
      position absolute
      z-index -1
    &.pink
      &:before
        background-color $color-pink
    &.blue
      &:before
        background-color $color-dark-blue
        background-color white
    .detail .content
      width calc(70% - 80px)
      @media(max-width: 768px)
        width calc(100% - 80px)
    .col
      float left
      padding 40px
      position relative
      width calc(70% - 80px)
      @media(max-width: 768px)
        width calc(100% - 80px)
      @media(max-width: 458px)
        padding 30px
        width calc(100% - 40px)
  .image
    background-image()
    pinned()
    animate()
    transform translateX(-50px) scale(0.8)
    background-size contain
    position absolute
    width 40%
    left auto
    right -10%
    top -40%
    bottom -40%
    @media(max-width: 768px)
      display none
  .detail
    background-color $color-lightest-grey
    padding 40px
    .content
      h3
        reset()
        margin-bottom 10px
        &:not(:first-child)
          margin-top 40px
      p
        reset()
</style>
