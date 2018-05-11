<template lang="pug">
.phone(:class="[position]")
  .screen(:style="{ 'background-image': `url(${url})` }")
</template>

<script>
export default {
  name: 'Panel',
  props: ['url', 'position']
}
</script>

<style lang="stylus" scoped>

@import '~stylus/shared'

.phone
  animate()
  box-shadow(0 0 5px 5px alpha(black, 0.05))
  pinned()
  transition-delay 0.1s
  background-color white
  position absolute
  overflow hidden
  left 70%
  right 2%
  top -10%
  @media(max-width: 768px)
    display none
  &:before, &:after
    radius(50%)
    background-color $color-lighter-grey
    content ''
    display none
    position absolute
    left 50%
    bottom 5px
    height 30px
    width 30px
    margin-left -15px
  &:before
    radius(1px)
    bottom auto
    top 10px
    height 2px
    width 32px
    margin-left -16px
  &.bottom
    bottom 0px
    border-top-left-radius 20px
    border-top-right-radius 20px
    &:before
      display block
    .screen
      border-top-left-radius 10px
      border-top-right-radius 10px
      bottom 0 !important
      background-position top
  &.top
    top 0px
    border-bottom-left-radius 20px
    border-bottom-right-radius 20px
    top 0
    bottom -10%
    &:after
      display block
    .screen
      border-bottom-left-radius 10px
      border-bottom-right-radius 10px
      top 0 !important
      background-position bottom
  .screen
    background-image($color-lightest-grey)
    background-position top center
    background-size 100% auto
    overflow hidden
    padding 1px
    position absolute
    top 20px
    bottom 40px
    left 10px
    right 10px
</style>
