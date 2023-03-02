<template>
  <div class="relative">
    <section id="sec5">
      <div class="box_pic">
        <div class="pic1"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
        >
          <img src="./S5/1.jpg" />
          <span class="pic_text">合成參考示意圖</span>
        </div>
        <div class="pic2">
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
          ><img src="./S5/2.jpg" />
           <span class="pic_text">校園第一排</span></div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="400"
            data-aos-duration="800"
          ><img src="./S5/3.jpg" />
           <span class="pic_text">福星公園</span></div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
          ><img src="./S5/4.jpg" />
          <span class="pic_text">文林國小</span></div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="400"
            data-aos-duration="800"
          ><img src="./S5/5.jpg" />
           <span class="pic_text">公園第一境</span></div>
        </div>
      </div>
      <div class="box_text">
        <div class="title"
          data-aos-once="false"
          data-aos="fade-in"
          data-aos-delay="0"
          data-aos-duration="800"
        >
          <img src="./S5/title.png" />
        </div>
        <div class="text">
          <!-- 1 -->
          <h2
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="0"
            data-aos-duration="800"
          >14%純住宅用地<br/>新富人特區 更勝大直重劃區</h2>
          <p
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="0"
            data-aos-duration="800"
            v-if="isMobile"
          >29坪，跨界3房卓越尺度，住大，何必買大；31坪，享受校園首排綠意，與豪宅平起平坐；37坪，邊間雙衛3房，大面寬採光舒適宜居；46坪，寧靜視野兼得，景觀豪宅無須坪數大。戶戶挑高3米5夢幻逸品，內斂鋒芒，靜謐安逸的名宅氣韻，構築未來科技聚落的高質感生活模式。</p>
          <p
            v-else
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="0"
            data-aos-duration="800"
          >北士科全區面積約94.38公頃，純住宅區卻僅占不到14％比例，珍稀價值不言而喻，交通、醫療、教育、休閒等機能完備，將是大北區最有質感的新富人名宅聚落。</p>
          <!-- 2 -->
          <h2
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
          >北士科正核心 靜謐街廓角地</h2>
          <p
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
            v-if="isMobile"
          >「宏普陽明」定址北士科正核心位置，純住宅新富人特區核心中的核心聚落，在車水馬龍的承德路、文林北路轉個彎，邂逅北科路上一處靜謐世外，珍稀難得的定靜街廓、完美角地。</p>
          <p
            v-else
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
          >「宏普陽明」定址北士科正核心位置，純住宅新富人特區核心中的核心聚落，在車水馬龍的承德路、文林北路轉個彎，邂逅北科路上一處靜謐世外，珍稀難得的定靜街廓、完美角地。</p>
          <!-- 3 -->
          <h2
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="400"
            data-aos-duration="800"
          >校園第一排 公園第一境 雙園正軸心</h2>
          <p
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="400"
            data-aos-duration="800"
          >「宏普陽明」近千坪基地，面對文林國小校園第一排，散步69米到北士科最大廣達3.29公頃的福星公園，雙享北士科正核心與雙園正軸心，<br
            v-if="isMobile" />悠然大隱寧境。</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
@import ./sass/share

@media screen and (min-width: $bp-pc)

@media screen and (max-width: $bp-mb)
// --------------------------------
// -- all
// --------------------------------
#sec5
  width: 80vw
  margin: 0 auto
  display: flex
  flex-direction: column
@media screen and (min-width: $bp-pc)
  #sec5
    padding-bottom: 10vw
    .box_pic
      order: 2
@media screen and (max-width: $bp-mb)
  #sec5
    padding: 13vw 0

// --------------------------------
// -- pic
// --------------------------------
$g: 15px
.box_pic
  display: flex
  img
    width: 100%
    height: 100%
.pic1
  position: relative
  .pic_text
    left: 1.5vw
    top: 1vw

.pic2
  display: flex
  flex-wrap: wrap
  div
    position: relative
    font-size: 0
    width: calc(50% - #{$g}/2)
    &:nth-child(1), &:nth-child(2)
      margin-bottom: $g
    &:nth-child(2), &:nth-child(4)
      margin-left: $g
  .pic_text
    background: rgba(0,0,0,.5)
    width: 100%
    bottom: 0

.pic_text
  font:
    size: calc(12 * 100vw / 375)
    family: "Noto Sans TC" !important
  position: absolute
  color: #fff
  display: flex
  align-items: center
  justify-content: center

@media screen and (min-width: $bp-pc)
  .box_pic

  .pic1
    width: 50%
    margin-right: $g
  .pic2
    width: 50%
  .pic_text
    height: 36px
    font:
     size: calc(16 * 100vw / 1920)

@media screen and (max-width: $bp-mb)
  .box_pic
    flex-direction: column
  .pic1
    margin-bottom: $g
  .pic2
  .pic_text
    height: 22px

// --------------------------------
// --title
// --------------------------------
.title
  margin: 0 auto
  img
    width: 100%
  .pic_text
    height: 22px

@media screen and (min-width: $bp-pc)
  .title
    width: 28vw
    margin-top: 3vw
@media screen and (max-width: $bp-mb)
  .title
    width: 54vw
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
    margin: 3vw 0
    font:
      size: calc(20 * 100vw / 1920)
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
      line-height:2
      letter-spacing: 0vw
      font:
          size: 1vw
          weight: 300

@media screen and (max-width: $bp-mb)
  .text
    p
      margin: 4vw 0 14vw

@media screen and (min-width: $bp-pc)

@media screen and (max-width: $bp-mb)
</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'

export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      isTablet,
      bMbOpen: false
    }
  },

  methods: {},

  created() {},

  mounted() {},

  computed: {}
}
</script>
