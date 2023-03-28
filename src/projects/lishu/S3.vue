<template>
  <div class="relative sec3">
    <section id="sec3">
      <div class="box"
        data-aos-once="false"
        data-aos="fade-up"
        data-aos-delay="0"
        data-aos-duration="800"
      >
        <div class="pre" @click="prevBtn"></div>
        <div class="nxt" @click="nextBtn"></div>
        <swiper :options="swiperOption" ref="swiper3">
          <swiper-slide v-for="item in list" :key="'s3' + item">
            <div class="gradient"></div>
            <div class="msg">{{ item }}</div>
          </swiper-slide>
        </swiper>
      </div>
      <ul class="dot">
        <li
          v-for="item in 3"
          :key="'dot' + item"
          @click="fnDotChange(item)"
        ></li>
      </ul>
      <div class="text">
        <h2
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
          data-aos-offset="-300"
        >國際都會的豐饒璀璨 總在水岸綻放</h2>
        <p
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
          data-aos-offset="-300"
        >一座偉大的城市，總有一條潺潺流淌的水岸，在河畔風情與繁華喧囂之間，構築這座都會的輝煌盛世，與高質感生活模式；例如紐約曼哈頓水岸豪宅群、法國巴黎塞納河左岸特區開發計畫、英國倫敦泰晤士河南岸開發計畫等 都是全球頂尖富豪們追逐鍾愛的置產舞台。</p>
      </div>
    </section>
  </div>
</template>

<script>
import $ from 'jquery'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

import { isMobile, isTablet } from '@/utils'

export default {
  name: 'swiper-example-thumbs-gallery',
  title: 's3',
  components: {
    Swiper,
    SwiperSlide
  },

  data() {
    return {
      list: [
        '巴黎塞納河左岸',
        '倫敦泰晤士河南岸',
        '紐約曼哈頓水岸',
        // some
      ],
      vm: this,
      isMobile,
      isTablet,
      swiperOption: {
        loop: true,
        breakpoints: {
          768: {
            spaceBetween: 0
          },
          0: {
            //slidesPerView: 0,
            spaceBetween: 14
          }
        },
        autoplay: {
          delay: 4000,
          disableOnInteraction: false
        },
        speed: 800,
        on: {
          slideChangeTransitionStart: function() {
            let eq = this.activeIndex
            if (eq >= 3) {
              eq = eq - 3
            }
            $('.dot li')
              .removeClass('active')
              .eq(eq)
              .addClass('active')
          }
        }
      }
    }
  },

  methods: {
    prevBtn() {
      this.$refs.swiper3.$swiper.slidePrev()
    },
    nextBtn() {
      this.$refs.swiper3.$swiper.slideNext()
    },
    fnDotChange(i) {
      let eq = i - 1
      if (eq >= 3) {
        eq = eq - 3
      }
      this.$refs.swiper3.$swiper.slideTo(eq)
    }
  },

  created() {},

  mounted() {},

  computed: {}
}
</script>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
@import ./sass/share
// ====================================
// == TEXT
// ====================================
.sec3
  background: #004A77BB
  &::before
    position: absolute
    content: ""
    display: block
    height: 20vw
    width: 100%
    background: linear-gradient(to top,  #004A77BB 0%, #004A7700 100%)
    bottom: 100%
    left: 0

.text
  width: 80vw
  margin: 0 auto
  color: #fff
  line-height: 1.5
  font:
    size: calc(12 * 100vw / 375)
  h2
    color: $yellow
    font:
      size: 1.25em
      weight: 600
  p
    font:
      family: "Noto Sans TC" !important
      weight: 300
@media screen and (min-width: $bp-pc)
  $g: 2vw
  .text
    width: 60vw
    position: relative
    display: flex
    flex-wrap: wrap
    line-height: 1.7
    font:
      size: calc(20 * 100vw / 1920)
    margin:
      top: 3vw
    &:after
      content: ""
      height: 100%
      left: 50%
      top: 0
      width: 1px
      background: #fff
      position: absolute
    p, h2
      width: 50%
      display: flex
      align-items: center
      justify-content: flex-end
      // margin-bottom: 3vw
    & > *
      &:nth-child(1), &:nth-child(2)
        // margin-top: 5vw
      &:nth-child(5), &:nth-child(6)
        margin-bottom: 5vw
    h2
      text-align: right
      padding-right: $g
      font:
        size: 1.63em
      line-height:1.4
    p
      padding-left: $g
      text-align: justify
      letter-spacing: 0vw

@media screen and (max-width: $bp-mb)
  .text
    margin-top: 7vw
    h2
      line-height: 1.5
    p
      font-size: 3.2vw
      margin: 4vw 0 10vw
      &:last-child
        margin:
          bottom: 20vw

// ====================================
// == SWIPER v
// ====================================

// 圖片
.swiper-slide
  background:
    position: 0 0
    size: contain
  position: relative

.swiper-slide
  &:nth-child(1), &:nth-child(4), &:nth-child(7)
    background-image: url('./S3/1.jpg')

  &:nth-child(2), &:nth-child(5), &:nth-child(8)
    background-image: url('./S3/2.jpg')

  &:nth-child(3), &:nth-child(6), &:nth-child(9)
    background-image: url('./S3/3.jpg')
@media screen and (min-width: $bp-pc)

@media screen and (max-width: $bp-mb)

// 架構
#sec3
  position: relative
  display: flex
  flex-direction: column
.box
  font-size: 0
  overflow: hidden

.swiper-container
  z-index: 2

@media screen and (min-width: $bp-pc)
  #sec3
    padding:
      top: 7vw
      bottom: 7vw
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 34.37vw // w * 0.562

  // w
  .swiper-container
    width:  68vw

@media screen and (max-width: $bp-mb)
  #sec3
    // padding-top: 20vw
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 51vw // w * 2.87

  // w
  .swiper-container
    // width: 80vw

  // gurter
  .box
    position: relative
    & > div
      //padding-left: calc( (100vw - 83vw) / 2 + 14px)

// --------------------------------
// PRE NEX
.box
  position: relative

.pre, .nxt
  display: block
  position: absolute
  width: 0
  padding-left: 18px!important
  height: 31px
  font:
    size: 20px
  z-index: 4
  cursor: pointer
  background:
    size: contain
  top: 50%
  transform: translateY(-50%)
  background:
    repeat: no-repeat

.pre
  background:
    image: url("./all/prev-btn.png")
    repeat: no-repeat

.nxt
  background:
    image: url("./all/next-btn.png")

@media screen and (min-width: $bp-pc)
  .pre,.nxt
    display: none

@media screen and (max-width: $bp-mb)
  $lr: 2vw
  .box
    position: relative
    &:before, &:after
      position: absolute
      content: ""
      width: 15vw
      height: 100%
      z-index: 3
      top: 0
    &:before
      left: 0
      //background-image: linear-gradient(to right, rgba(0,74,119,.8), rgba(0,74,119,0))
    &:after
      //background-image: linear-gradient(to left, rgba(0,74,119,.8), rgba(0,74,119,0))
      right: 0
  .pre
    left: $lr

  .nxt
    right: $lr

// --------------------------------
// dot
$w: 10px
@media screen and (min-width: $bp-pc)
  .dot
    position: absolute
    display: flex
    justify-content: center
    height: 6px
    width: 10vw
    left: 50%
    top: 39.8vw
    transform: translateX(-50%)
    z-index: 9
    li
      border: solid 1px #fff
      width: 30%
      position: relative
      cursor: pointer
      margin-right: 5%
      &:last-child
        margin: 0
      &.active
        cursor: default
        background: #fff

@media screen and (max-width: $bp-mb)
  .dot
    display: none

// ====================================
// == msg
// ====================================
.gradient
  position: absolute
  width: 100%
  height: 10vw
  bottom: 0
  background-image: linear-gradient(to top, rgba(0,0,0,.8), rgba(0,0,0,0))
.msg
  position: absolute
  left: 10px
  bottom: 10px
  color: #fff
  font-size: 13px
</style>
