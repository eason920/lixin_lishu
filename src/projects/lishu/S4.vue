<template>
  <div class="relative">
    <section id="sec4">
      <div class="title"
        data-aos-once="false"
        data-aos="fade-in"
        data-aos-delay="0"
        data-aos-duration="800"
      >
        <img src="./S4/title.png" />
      </div>
      <div class="text">
        <div class="text1"><span>頂級醫療 國際學校</span> <span>新富生活 等高對位</span></div>
        <div class="text2">
          鄰近新光、榮總、振興、陽明、和信…匯聚頂尖醫療資源就近守護；歐洲學校、美國學校、日僑學校…文教優質環境，等高對位新富貴族生活質地。
        </div>
      </div>
      <div class="box">
        <swiper :options="swiperOptions">
          <swiper-slide v-for="(item, i) in swipList" :key="'box' + i">
            <div class="box_item">
              <div class="box_text">{{ item }}</div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </section>
  </div>
</template>

<style lang="sass" scoped>
@import src/assets/style/myvar
@import ./sass/share
// 圖片
@media screen and (min-width: $bp-pc)
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(8), &:nth-child(15)
      background-image: url('./S4/1.jpg')

    &:nth-child(2), &:nth-child(9), &:nth-child(16)
      background-image: url('./S4/2.jpg')

    &:nth-child(3), &:nth-child(10), &:nth-child(17)
      background-image: url('./S4/3.jpg')

    &:nth-child(4), &:nth-child(11), &:nth-child(18)
      background-image: url('./S4/4.jpg')
    &:nth-child(5), &:nth-child(12), &:nth-child(19)
      background-image: url('./S4/5.jpg')
    &:nth-child(6), &:nth-child(13), &:nth-child(20)
      background-image: url('./S4/6.jpg')
    &:nth-child(7), &:nth-child(14), &:nth-child(21)
      background-image: url('./S4/7.jpg')

@media screen and (max-width: $bp-mb)

  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(8), &:nth-child(15)
      background-image: url('./S4/3.jpg')

    &:nth-child(2), &:nth-child(9), &:nth-child(16)
      background-image: url('./S4/4.jpg')

    &:nth-child(3), &:nth-child(10), &:nth-child(17)
      background-image: url('./S4/5.jpg')

    &:nth-child(4), &:nth-child(11), &:nth-child(18)
      background-image: url('./S4/6.jpg')
    &:nth-child(5), &:nth-child(12), &:nth-child(19)
      background-image: url('./S4/7.jpg')
    &:nth-child(6), &:nth-child(13), &:nth-child(20)
      background-image: url('./S4/1.jpg')
    &:nth-child(7), &:nth-child(14), &:nth-child(21)
      background-image: url('./S4/2.jpg')

// 總高
@media screen and (min-width: $bp-pc)
  .swiper-container, // height 1
  .swiper-wrapper,
  .swiper-slide,
  .box_item
    height: 20vw
    // max-height: 70vh
@media screen and (max-width: $bp-mb) and (orientation: portrait)
  .swiper-container,
  .swiper-wrapper,
  .swiper-slide,
  .box_item
    height: 50vw

@media screen and (max-width: $bp-mb) and (orientation: landscape)
  .swiper-container,
  .swiper-wrapper,
  .swiper-slide,
  .box_item
    height: 100vh

// --------------------------------
// -- 我內部介面
// --------------------------------
#sec4
  position: relative
  z-index: 10
  display: flex
  flex-direction: column
.box

.box_item
  position: relative
.box_text
  font:
    size: 1vw
    family: "Noto Sans TC" !important
    size: calc(12 * 100vw / 375)
  position: absolute
  width: 100%
  bottom: 0
  color: #fff
  background: rgba(0,0,0,.5)
  display: flex
  align-items: center
  justify-content: center

@media screen and (min-width: $bp-pc)
  #sec4

  .box
    margin:
      left: 10vw
      bottom: 6vw
    width: 90vw
  .box_text
    height: 36px
    font:
      size: calc(20 * 100vw / 1920)

@media screen and (max-width: $bp-mb)
  .box
    width: 120vw
    margin:
      left: -2vw
    order: 1
  .title
    order: 2
  .text
    order: 3
  .box_text
    height: 22px

// --------------------------------
// --title
// --------------------------------
.title
  margin: 0 auto
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .title
    width: 45vw
    margin-top: 3vw
@media screen and (max-width: $bp-mb)
  .title
    width: 80vw
    margin:
      top: 7vw
      bottom: 5vw

// --------------------------------
// -- text
// --------------------------------
.text
  color: #fff
  line-height: 1.5
  font:
    size: calc(12 * 100vw / 375)
.text1
  font:
    size: 1.25em
    weight: 600

.text2
  font:
    family: "Noto Sans TC" !important
    weight: 300
@media screen and (min-width: $bp-pc)
  $g: 1.5vw
  .text
    display: flex
    flex-direction: row
    width: 80vw
    margin: 2vw auto
    line-height: 1.7
    font:
      size: calc(20 * 100vw / 1920)
  .text1
    width: 50%
    border-right: solid 1px #fff
    text-align: right
    padding: 1.5vw 0
    padding-right: $g
    font:
      size: 1.63em
    span
      letter-spacing: .2vw
  .text2
    width: 50%
    padding-left: $g
    text-align: justify
    font-size: 1vw
    display: flex
    align-items: center

@media screen and (max-width: $bp-mb)
  .text

  .text1
    margin-bottom: 2vw
    span
      display: block
      text-align: center
      line-height: 1.5
      letter-spacing: .06em
  .text2
    text-align: center
    width: 80vw
    margin: 0 auto
    margin:
      bottom: 10vw
</style>

<script>
import { isMobile, isTablet } from '@/utils'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
  name: 'section1',

  components: {
    Swiper,
    SwiperSlide
  },

  data() {
    return {
      isMobile,
      isTablet,
      bIsOpen: false,
      swipList: [
        '日僑學校',
        '歐洲學校',
        '陽明醫院',
        '振興醫院',
        '新光醫院',
        '榮民總醫院',
        '美國學校'
      ],
      swiperOptions: {
        breakpoints: {
          // when window width is >= 320px
          768: {
            slidesPerView: 4.5,
            spaceBetween: 15
          },
          // when window width is >= 640px
          0: {
            slidesPerView: 2.3,
            spaceBetween: 10
          }
        },
        // slidesPerView: 4.5,
        // spaceBetween: 15,
        loop: true, // 是否 slide 後循環
        // initialSlide: 0, // 最初 pic index
        // slidesPerView: 'auto',
        autoplay: {
          delay: 1500,
          disableOnInteraction: false // 換頁後是否停止 autoplay
        },
        speed: 1600,
        grabCursor: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
          type: 'bullets'
        },
      }
    }
  },

  methods: {},

  created() {},

  mounted() {},

  computed: {}
}
</script>
