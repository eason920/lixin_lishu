<template>
  <div class="relative">
    <section id="sec7">
      <div class="box_pic">
        <div class="pic1"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-delay="0"
          data-aos-duration="800"
        >
          <img src="./S7/1.jpg" />
          <span class="pic_text">大安區 和苑三井花園飯店</span>
        </div>
        <div class="pic2">
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
          ><img src="./S7/2.jpg" />
           <span class="pic_text">大安區 宏普PARK</span></div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="400"
            data-aos-duration="800"
          ><img src="./S7/3.jpg" />
           <span class="pic_text">信義計劃區 新川普</span></div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="200"
            data-aos-duration="800"
          ><img src="./S7/4.jpg" />
          <span class="pic_text">大直重劃區明水富御</span></div>
          <div
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="400"
            data-aos-duration="800"
          ><img src="./S7/5.jpg" />
           <span class="pic_text">中山區 宏普頤和</span></div>
        </div>
      </div>
      <div class="box_text">
        <div class="title"
          data-aos-once="false"
          data-aos="fade-in"
          data-aos-delay="0"
          data-aos-duration="800"
        >
          <img src="./S7/title.png" />
        </div>
        <div class="text">
          <!-- 1 -->
          <h2
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="0"
            data-aos-duration="800"
          >宏觀建築 專鑄經典 <br
            v-if="isMobile" />日本三井不動產指定合作</h2>
          <p
            data-aos-once="false"
            data-aos="fade-up"
            data-aos-delay="0"
            data-aos-duration="800"
          >深耕建築35年，績優上市建商，全台高質感建築首席「宏普建設」，與日本三井不動產在忠孝新生站旁合作三井海外第一間飯店—「和苑三井花園飯店」，國際跨界領導品牌看見宏普真價值，攜手引領世界建築走進台灣！</p>
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
#sec7
  width: 80vw
  margin: 0 auto
  display: flex
  flex-direction: column
@media screen and (min-width: $bp-pc)
  #sec7
    padding-bottom: 10vw
    .box_pic
      order: 2
@media screen and (max-width: $bp-mb)
  #sec7
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
    height: 36px

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
    line-height: 1.7
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
      text-align: left
      letter-spacing: 0vw

@media screen and (max-width: $bp-mb)
  .text
    h2
      line-height: 1.5
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
