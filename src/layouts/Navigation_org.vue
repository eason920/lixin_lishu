<template>
  <div class="menu" :class="[{ navBgBlack: bAddClass }]">
    <img src="../projects/lishu/S1/logo_pc.png" id="logo" :class="[{isOpacity1: bAddClass}]"/>
    <div>
        <ul>
          <li
          :key="item.name"
          v-scroll-to="{
            element: `#${item.section}`,
            offset: item.offset ? item.offset : offset
          }"
          v-for="item in list"
        >
        <a href="#" @click.prevent="">{{ item.name }}</a>
      </li>
      <div class="appoint">即刻預約</div>
    </ul>
  </div>
  </div>
</template>

<script>
import $ from 'jquery'
import { isMobile, isTablet } from '@/utils'
import navList from '@/info/navList'

export default {
  name: 'navigation',
  components: {},
  data() {
    return {
      isOpen: false,
      isMobile,
      isTablet,
      list: navList,
      bAddClass: false
    }
  },

  computed: {
    offset() {
      if (this.isMobile) {
        return -39
      }

      if (this.isTablet) {
        return -45
      }

      return -56
    }
  },

  mounted() {
    const h = $(window).height() - 200
    if (!isMobile) {
      if ($(window).scrollTop() > h) {
        this.bAddClass = true
      }
      $(window).scroll(() => {
        this.bAddClass = $(window).scrollTop() > h
      })
    }

    $('.appoint').click(() => {
      $('html,body').animate({ scrollTop: $('#contact').offset().top }, 1000)
    })
  }
}
</script>

<style lang="sass" scoped>
@import ../projects/lishu/sass/share
// nav
%text
  text-decoration: none
  letter-spacing: .5vw
  color: $b
  font:
    size: 1vw
    family: "Noto Sans TC" !important
#logo
  opacity: .5
  transition: .3s
  height: 46px
  &.isOpacity1
    opacity: 1

.menu
  padding: 0 4.5vw
  position: fixed
  top: 0
  left: 0
  display: flex
  z-index: 9999
  width: 100%
  align-items: center
  justify-content: space-between
  height: 115px
  transition: background .3s
  ul
    display: flex
    justify-content: flex-end
    align-items: center
    gap: 1.6vw
  li
    a
      display: block
      padding: 14px 0
      text-decoration: none
      @extend %text
      position: relative
      transition: color .3s
      white-space: nowrap
      &:after
        content: ""
        position: absolute
        bottom: 0
        left: 0
        display: block
        width: calc(100% - 5px)
        height: 2px
        background-color: #2BB8FF
        opacity: .6
        transform: scaleX(0)
        transition: transform .4s ease
        transform-origin: 0% 50%
      &:hover:after
        transform: scaleX(1)
  // white
  &.navBgBlack
    background-color: rgba(0,0,0,.5)
    z-index: 99
.appoint
  @extend %text
  @include classicHover
  transition: .3s
  padding: 15px 6px 15px 15px
  white-space: nowrap

</style>
