<template>
  <div class="relative">
    <section id="sec2">
      <ball class="ball is1" />
      <ball2 class="ball is2" />
      <!-- PC -->
      <div class="is_pc" v-if="!isMobile">
        <div class="logo" data-aos-once="false" data-aos="fade-up" data-aos-delay="0" data-aos-duration="1400">
          <img src="./S2/logo_right.png" />
        </div>
        <div data-aos-once="false" data-aos="fade-up" data-aos-delay="0" data-aos-duration="1400">
          <img class="subtitle" src="./all/subtitle.png" />
        </div>
      </div>
      <!-- MB -->
      <div class="is_mb" v-else>
        <div class="logo" data-aos-once="false" data-aos="fade-up" data-aos-delay="0" data-aos-duration="1400">
          <img src="./S2/logo_right.png" />
        </div>
        <div class="subtitle" data-aos-once="false" data-aos="fade-up" data-aos-delay="0" data-aos-duration="1400">
          <img src="./all/subtitle.png" />
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
@import ./sass/share

@media screen and (min-width: $bp-pc)
  #sec2
    // height: 56.25vw
    height: 100vh
    overflow: hidden
    min-height: calc(100vw * 900 / 1920)
    max-height: calc(100vw * 1080 / 1920)
    background:
      image: url(./S2/bg_pc.png)
      size: contain
      color: #004A77
  .is_pc
    position: absolute
    left: 12vw
    top: 19vw
    .logo
      width: 40vw
      img
        width: 100%
    .subtitle
      width: 37vw
      margin-left: 1.7vw
      display: flex

@media screen and (max-width: $bp-mb)
  #sec2
    background:
      image: url(./S2/bg_mb.png)
      size: cover
      color: #004A77
      position: center
  .is_mb
    height: 50vh
    & > div
      position: absolute
      z-index: 1
    img
      width: 100%
    .logo
      width: 75vw
      left: 5vw
      top: 38vw
    .subtitle
      width: 88vw
      left: 6vw
      bottom: 8vw

// ====================================
// == ball
// ====================================
.ball
  position: absolute
  z-index: 1
@media screen and (min-width: $bp-pc)
  .ball
    &.is1
      width: 45px
      height: 45px
      left: 8.5vw
      top: 31vw
    &.is2
      width: 47px
      height: 47px
      left: 38vw
      top: 20vw
@media screen and (max-width: $bp-mb)
  .ball
    &.is1
      width: 25px
      height: 25px
      left: 3vw
      top: 60vw
    &.is2
      width: 25px
      height: 25px
      left: 52vw
      top: 24vw

</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'
import $ from 'jquery'
import ball from './ball.vue'
import ball2 from './ball2.vue'
export default {
  name: 'section1',
  components: {
    ball,
    ball2,
  },
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
