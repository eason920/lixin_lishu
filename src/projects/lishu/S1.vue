<template>
  <div class="relative">
    <section id="sec1">
      <!-- PC -->
      <div class="share_box is_pc" v-if="!isMobile">
        <video autoplay loop muted>
          <source src="https://h35.banner.tw/lishu/123.mp4">
        </video>
        <div class="logo_pc" data-aos-once="false" data-aos="fade-up" data-aos-delay="500" data-aos-duration="1400">
          <img loading="lazy" src="./S1/logo_pc_left.png" />
        </div>
        <div class="title">
          <div data-aos-once="false" data-aos="fade-up" data-aos-delay="0" data-aos-duration="2000">
            <img loading="lazy" class="title_img1" src="./all/subtitle.png" />
          </div>
          <div data-aos-once="false" data-aos="fade-right" data-aos-delay="1000" data-aos-duration="1800">
            <div class="title_box">
              <img loading="lazy" class="title_box_img2" src="./S1/appoint_pc.png" />
            </div>
          </div>
        </div>
      </div>
      <!-- MB -->
      <div class="share_box is_mb" v-else>
        <!-- <video autoplay loop muted>
          <source src="https://h35.banner.tw/lishu/123.mp4">
        </video> -->
        <img loading="lazy" class="demo" src="./S1/bg_mb.jpg" />
        <div class="logo_mb"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="2000"
        >
          <img loading="lazy" src="./S1/logo_mb.png" />
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
@import ./sass/share
.share_box
  position: relative
  height: 100%
video
  object-fit: fill
  height: 100%
  width: 100%
  position: absolute
  top: 0
  left: 0
@media screen and (min-width: $bp-pc)
  #sec1
    // height: 56.25vw
    height: 100vh
    overflow: hidden
    min-height: calc(100vw * 900 / 1920)
    max-height: calc(100vw * 1080 / 1920)
    background:
      color: gray
  .is_pc
    .logo_pc
      position: absolute
      right: 4vw
      top: 19vw
      width: 50vw
      img
        width: 100%
    .title
      position: absolute
      bottom: 0
      right: 6vw
      display: flex
      padding:
        bottom: 3vw
      z-index: 2
    .title_img1
      width: 30vw // title height
      margin:
        right: 2vw
    .title_box
      @include classicHover
      transition: .3s
      padding: 0 23px
      display: flex
      align-items: center
      height: 100%
    .title_box_img2
      width: 9vw
      margin-bottom: .5vw

@media screen and (max-width: $bp-mb)
  #sec1
    // height: calc( 100vh - 63px )
  .is_mb
    .demo
      width: 100%
      height: auto
    .logo_mb
      position: absolute
      top: 30vw
      left: 5vw
      width: 90vw
      img
        width: 100%

</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'
import $ from 'jquery'
export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      isTablet
    }
  },

  methods: {},

  created() { },

  mounted() {
    $('.title_box,.appoint').click(() => {
      $('html,body').animate({ scrollTop: $('#contact').offset().top }, 1000)
    })
  },
  computed: {}
}
</script>
