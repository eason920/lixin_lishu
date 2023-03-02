<template>
  <div class="relative">
    <section id="sec1">
      <!-- PC -->
      <div class="share_box is_pc" v-if="!isMobile">
        <video autoplay loop muted>
          <source src="https://h35.banner.tw/lishu/123.mp4">
        </video>
        <div class="title">
          <div
            data-aos-once="false"
            data-aos="fade-in"
            data-aos-delay="500"
            data-aos-duration="1400"
          >
            <img class="title_img1" src="./S1/title_pc.png" />
          </div>
          <div
            data-aos-once="false"
            data-aos="fade-in"
            data-aos-delay="1000"
            data-aos-duration="1800"
          >
            <div class="title_box">
              <img class="title_box_img2" src="./S1/appoint_pc.png" />
            </div>
          </div>
        </div>
        <div class="title_bg"></div>
      </div>
      <!-- MB -->
      <div class="share_box is_mb" v-else>
        <div class="above">
          <video style="width= 100%; height=100%; object-fit: fill" autoplay loop muted>
            <source src="./S1/portrait.mp4">
          </video>
        </div>
        <div class="under">
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="0"
            data-aos-duration="1800"
            class="logo"
          >
            <img src="./all/logo.png" />
          </div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="300"
            data-aos-duration="1800"
            class="title"
          >
            <img src="./S1/title_mb.png" />
          </div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="600"
            data-aos-duration="2000"
            class="appoint"
          >
            <img src="./S1/appoint_mb.png" />
          </div>
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
  width: 100%
  position: absolute
  top: 0
  left: 0
@media screen and (min-width: $bp-pc)
  #sec1
    // height: 56.25vw
    height: 115vh
    min-height: calc(100vw * 900 / 1920)
    max-height: calc(100vw * 1080 / 1920)
    background:
      color: gray
  .is_pc
    .title
      position: absolute
      bottom: 0
      left: 50%
      transform:  translateX(-50%)
      display: flex
      padding:
        bottom: 3vw
      z-index: 2
    .title_img1
      width: 63vw // title height
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
      width: 12vw
    .title_bg
      height: 15vh
      background-image: linear-gradient(to top,rgba(0,0,0,1) 20%, rgba(0,0,0,.5) 85%, rgba(0,0,0,0))
      position: absolute
      bottom: 0
      z-index: 1
      width: 100%
@media screen and (max-width: $bp-mb)
  #sec1
    // height: calc( 100vh - 63px )
  .is_mb
    display: flex
    flex-direction: column
    .above
      font-size: 0
      position: relative
      height: 100vh
      &:after
        content: ""
        position: absolute
        left: 0
        bottom: 0
        width: 100%
        height: 8vh
        background-image: linear-gradient(to top, rgba(0,0,0,1) 20%, rgba(0,0,0,.5) 60%, rgba(0,0,0,0))
      img
        width: 100%

    .under
      background-color: #000
      padding:
        bottom: 8vw
      div
        margin: 0 auto 6vw
      .logo
        width: 60vw
        img
         width: 100%
      .title
        width: 80vw
        img
          width: 100%
      .appoint
        @include classicHover
        width: 60vw
        padding: 3vw 0 3.5vw
        img
          width: 80%

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

  created() {},

  mounted() {
    $('.title_box,.appoint').click(() => {
      $('html,body').animate({ scrollTop: $('#contact').offset().top }, 1000)
    })
  },
  computed: {}
}
</script>
