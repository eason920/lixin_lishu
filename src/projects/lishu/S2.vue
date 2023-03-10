<template>
  <div class="relative">
    <section id="sec2">
      <div class="water_fixed">
        <water class="water" />
      </div>
      <div class="water_mo" v-if="isMobile">
        <water class="water" />
      </div>
      <div class="box"></div>
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
      <img class="diamond" src="./S2/diamond.png" />
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
      // image: url(./S2/bg_pc.png)
      size: contain
      color: #004A77
  .is_pc
    position: absolute
    left: 12vw
    // top: 19vw
    top: calc(50% - 7.5vw)
    z-index: 3
    .logo
      width: 35vw
      img
        width: 100%
    .subtitle
      width: 37vw
      margin-left: 1.7vw
      display: flex

@media screen and (max-width: $bp-mb)
  #sec2
    background:
      // image: url(./S2/bg_mb.png)
      size: cover
      color: #004A77
      position: center
  .is_mb
    position: relative
    height: calc(100vw * 443 / 375)
    z-index: 3
    & > div
      position: absolute
      z-index: 1
    img
      width: 100%
    .logo
      width: 64vw
      left: 8vw
      top: 37vw
    .subtitle
      width: 81vw
      left: 10vw
      bottom: 25vw

// ====================================
// == ball
// ====================================
.diamond
  position: absolute
  width: 16vw
  right: 18vw
  top: calc(50% - 11vw)
  z-index: 2
.water_fixed
  position: fixed
  left: 0
  top: 0
  width: 100%
  height: 100vh
  min-height: calc(100vw * 900 / 1920)
  max-height: calc(100vw * 1080 / 1920)

.water
  position: absolute
  left: 0vw
  top: calc(50% - 11vw)
  width:100vw
.ball
  position: absolute
  z-index: 2
.box
  position: absolute
  width: 100%
  height: 100%
  &::after,&::before
    position: absolute
    content: ""
    display: block
    height: 100%
  &::after
    left: 0
    width: 40%
    background: linear-gradient(to right,  #004A77FF 0%, #004A7700 100%)
    z-index: 2
    transform: skewX(-15deg)
    transform-origin: 0 0
  &::before
    right:0
    width: 70%
    background: radial-gradient(100% 100% at 120% 30%, #004A77FF 30%,  #004A7700 90%)
    z-index: 2
    // transform: skewX(20deg)
    // transform-origin: 0 0
    

@media screen and (min-width: $bp-pc)
  .ball
    &.is1
      width: 45px
      height: 45px
      left: 8.5vw
      top: calc(50% + 3.8vw)
    &.is2
      width: 47px
      height: 47px
      left: 38vw
      top: 20vw
      top: calc(50% - 8.5vw)
@media screen and (max-width: $bp-mb)
  .diamond
    width: 27vw
    right: 8vw
    top: 25vw
  .water_fixed
    min-height: calc(100vw * 667 / 375)
    max-height: calc(100vw * 812 / 375)
    .water
      top: calc(50% - 40vw)
      left: -30vw
      width:200vw
      transform: rotate(-35deg)
      
  .water_mo
    position: absolute
    left: 0
    top: 0
    width: 100%
    height: calc(100vw * 443 / 375)
    min-height: 0
    max-height: calc(100vw * 812 / 375)
    background: linear-gradient(to bottom,  #004A77FF 80%, #004A77BB 100%)

    
  .ball
    &.is1
      width: 25px
      height: 25px
      left: 8vw
      top: 60vw
    &.is2
      width: 25px
      height: 25px
      left: 42vw
      top: 25vw

</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'
import $ from 'jquery'
import water from './water.vue'
import ball from './ball.vue'
import ball2 from './ball2.vue'
export default {
  name: 'section1',
  components: {
    water,
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
