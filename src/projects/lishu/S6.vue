<template>
  <div class="relative">
    <section id="sec6">
      <div class="title"
        data-aos-once="false"
        data-aos="fade-in"
        data-aos-delay="0"
        data-aos-duration="800"
      >
        <img src="./S6/title.png" />
      </div>
      <div class="text">
        <!-- 1 -->
        <h2
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
        >高坪效精緻美型宅 高得房率 獨具競爭力</h2>
        <p
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
          v-if="!isMobile"
        >29坪，跨界3房卓越尺度，住大，何必買大；31坪，享受校園首排綠意，與豪宅平起平坐；37坪，邊間雙衛3房，大面寬採光舒適宜居；46坪，寧靜視野兼得，景觀豪宅無須坪數大。戶戶挑高3米5夢幻逸品，內斂鋒芒，靜謐安逸的名宅氣韻，構築未來科技聚落的高質感生活模式。</p>
        <p
          v-else
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
        >29~46坪高坪效3~3+1房皆採雙人房規劃，挑高3米5宜人尺度、開放餐廚、雙衛浴開窗…高得房率、獨具競爭力的精緻美型空間，已成為周邊醫療生技科技、企業高階、學校老師…置產北士科首選標的！</p>
        <!-- 2 -->
        <h2 v-if="!isMobile"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="200"
          data-aos-duration="800"
        >島嶼秘境 露天泳池 星級飯店奢雅時光饗宴</h2>
        <h2 v-if="isMobile"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="200"
          data-aos-duration="800"
        >島嶼秘境 露天泳池<br>星級飯店奢雅時光饗宴</h2>
        <p
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="200"
          data-aos-duration="800"
        >三進式動線從迎賓門廳、交誼廳，打造日系人文閱讀生活場域；北士科難得一見的露天秘境泳池，以島嶼風情、飯店質感譜寫北士科靜謐生活賦格。</p>
      </div>
      <div class="box">
        <div class="pre" @click="prevBtn"></div>
        <div class="nxt" @click="nextBtn"></div>
        <swiper :options="swiperOption" ref="swiper6">
          <swiper-slide v-for="item in 4" :key="'s6' + item"> </swiper-slide>
        </swiper>
      </div>
      <div class="m_msg" v-if="isMobile">
        宏普陽明樣品屋實景攝影<br/>
        (僅供裝潢參考，實際坪數，格局尺度依買賣合約書為準)
      </div>
      <ul class="dot">
        <li
          v-for="item in 4"
          :key="'dot' + item"
          @click="fnDotChange(item)"
        ></li>
      </ul>
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
  title: 'Thumbs gallery with Two-way control',
  components: {
    Swiper,
    SwiperSlide
  },

  data() {
    return {
      vm: this,
      isMobile,
      isTablet,
      swiperOption: {
        loop: true,
        breakpoints: {
          768: {
            spaceBetween: 30
          },
          0: {
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
            if (eq >= 4) {
              eq = eq - 4
            }
            $('.dot li')
              .removeClass('active')
              .eq(eq)
              .addClass('active')
            if (eq === 3) {
              $('.m_msg').css('opacity', 0)
            } else {
              $('.m_msg').css('opacity', 1)
            }
          }
        }
      }
    }
  },

  methods: {
    prevBtn() {
      this.$refs.swiper6.$swiper.slidePrev()
    },
    nextBtn() {
      this.$refs.swiper6.$swiper.slideNext()
    },
    fnDotChange(i) {
      let eq = i - 1
      if (eq >= 5) {
        eq = eq - 5
      }
      this.$refs.swiper6.$swiper.slideTo(eq)
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
// == TITLE
// ====================================
.title
  margin: 0 auto
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .title
    width: 22vw
    margin-top: 3vw
@media screen and (max-width: $bp-mb)
  .title
    width: 46vw
    margin:
      top: 7vw
      bottom: 5vw

// ====================================
// == TEXT
// ====================================
.text
  width: 80vw
  margin: 0 auto
  color: #fff
  line-height: 1.5
  font:
    size: calc(12 * 100vw / 375)
  h2
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
    position: relative
    display: flex
    flex-wrap: wrap
    line-height: 1.7
    font:
      size: calc(20 * 100vw / 1920)
    margin:
      top: 3vw
      bottom: 3vw
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
      margin-bottom: 3vw
    & > *
      &:nth-child(1), &:nth-child(2)
        margin-top: 5vw
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

@media screen and (min-width: $bp-pc)
  .swiper-slide
    &:nth-child(1), &:nth-child(5)
      background-image: url('./S6/1.png')

    &:nth-child(2), &:nth-child(6)
      background-image: url('./S6/2.png')

    &:nth-child(3), &:nth-child(7)
      background-image: url('./S6/3.png')

    &:nth-child(4)
      background-image: url('./S6/4.png')

@media screen and (max-width: $bp-mb)
  .swiper-slide
    &:nth-child(1), &:nth-child(5)
      background-image: url('./S6/m1.png')
      background-size: cover

    &:nth-child(2), &:nth-child(6)
      background-image: url('./S6/m2.png')
      background-size: cover

    &:nth-child(3), &:nth-child(7)
      background-image: url('./S6/m3.png')
      background-size: cover

    &:nth-child(4)
      background-image: url('./S6/m4.png')
      background-size: cover

// 架構
#sec6
  position: relative
  display: flex
  flex-direction: column
.box
  font-size: 0
  overflow: hidden

.swiper-container
  z-index: 2

@media screen and (min-width: $bp-pc)
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 45vw // w * 0.562

  // w
  .swiper-container
    width:  80vw

@media screen and (max-width: $bp-mb)
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 167vw // w * 2.87

  // w
  .swiper-container
    width: 80vw

  // gurter
  .box
    position: relative
    order: 1
  .m_msg
    order: 2
  .dot
    order: 3
  .title
    order: 4
  .text
    order: 5

// --------------------------------
// PRE NEX
.box
  position: relative

.pre, .nxt
  display: block
  position: absolute
  width: .5em
  height: 1.55em
  font:
    size: 20px
  z-index: 3
  cursor: pointer
  background:
    size: contain
  top: 50%
  transform: translateY(-50%)

.pre
  background:
    image: url("./S6/pre.png")

.nxt
  background:
    image: url("./S6/nxt.png")

@media screen and (min-width: $bp-pc)
  $lr: 5vw
  .pre
    left: $lr

  .nxt
    right: $lr

@media screen and (max-width: $bp-mb)
  $lr: 2vw
  .pre
    left: $lr

  .nxt
    right: $lr

// --------------------------------
// dot
$w: 10px
.dot
  display: flex
  justify-content: center
  height: 5px
  li
    width: 25%
    position: relative
    &:after
      content: ""
      position: absolute
      top: 2px
      left: 0
      width: 100%
      border-bottom: solid 1px #9FD9F6
    cursor: pointer
    &.active
      cursor: default
      background: #9FD9F6

@media screen and (min-width: $bp-pc)
  .dot
    width: 30vw
    margin-left: 59.5vw
    margin:
      top: 2vw
      bottom: 7vw

@media screen and (max-width: $bp-mb)
  .dot
    width: 80vw
    margin: 0 auto
    margin:
      top: 7vw
      bottom: 3vw
// --------------------------------
// MB msg
@media screen and (max-width: $bp-mb)
  .m_msg
    color: #9FD9F6
    font:
      size: 1vw
      family: "Noto Sans TC" !important
    line-height: 1.7
    width: 80vw
    margin: 0 auto
    margin-top: 5vw
</style>
