<template>
  <div class="home no-padding-top">
    <Loading :loading="load" />
    <SideNavigation v-if="isSide" />
    <Navigation v-if="!isMobile" />
    <MClose v-else />
    <!-- <Indigator :viewIndex="viewIndex" /> -->
    <!-- <full-page
      ref="fullPage"
      :options="options"
      id="fullpage"
    > -->
    <!-- <vue-lazy-component class="section" id="sectionDe" @init="init">
      <SwiperDemo />
    </vue-lazy-component>
    <div class="sbg">
      <img class="is_mb" src="../projects/lishu/all/sbg_mb.png" />
      <img class="is_pc" src="../projects/lishu/all/sbg_pc.png" />
    </div> -->
   <!-- <vue-lazy-component class="section" id="section1" style="" @init="init">
      <S1 />
    </vue-lazy-component>  -->
    <vue-lazy-component class="section" id="section2" @init="init">
      <S2 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section3" @init="init">
      <S3 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section4" @init="init">
      <S4 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section5" @init="init">
      <S5 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section6" @init="init">
      <S6 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section7" @init="init">
      <S7 />
    </vue-lazy-component>
    <!--vue-lazy-component class="section" id="section8" @init="init">
      <S8 />
    </vue-lazy-component-->
    <vue-lazy-component class="section" id="section9" @init="init">
      <S9 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="contact">
      <ContactSection />
    </vue-lazy-component>
    <!-- ======================== -->
    <MobileNav />
  </div>
</template>

<script>
// @ is an alias to /src
import $ from 'jquery'
import Navigation from '@/layouts/Navigation.vue'
import { isMobile } from '@/utils'
import SideNavigation from '@/layouts/SideNavigation.vue'
import ContactSection from '@/layouts/ContactSection.vue'
import MobileNav from '@/layouts/MobileNav.vue'
import Loading from '@/components/Loading.vue'
// import Indigator from '@/components/Indigator.vue'
// import SwiperDemo from '@/projects/lishu/swiperDemo_S7_single.vue'
import MClose from '@/projects/lishu/MClose.vue'
// import S1 from '@/projects/lishu/S1.vue'
import S2 from '@/projects/lishu/S2.vue'
import S3 from '@/projects/lishu/S3.vue'
import S4 from '@/projects/lishu/S4.vue'
import S5 from '@/projects/lishu/S5.vue'
import S6 from '@/projects/lishu/S6.vue'
import S7 from '@/projects/lishu/S7.vue'
//import S8 from '@/projects/lishu/S8.vue'
import S9 from '@/projects/lishu/S9.vue'

export default {
  name: 'home',
  components: {
    Loading,
    // Indigator,
    Navigation,
    SideNavigation,
    ContactSection,
    MobileNav,
    // SwiperDemo,
    MClose,
    // S1,
    S2,
    S3,
    S4,
    S5,
    S6,
    S7,
    //S8,
    S9
  },

  data() {
    return {
      isMobile,
      isSide: false,
      load: true,
    }
  },
  created() {
    $(document).ready(() => {
      // Images loaded is zero because we're going to process a new set of images.
      var imagesLoaded = 0
      // Total images is still the total number of <img> elements on the page.
      var totalImages = $('img').length

      const allImagesLoaded = () => {
        this.load = false
      }
      const imageLoaded = () => {
        imagesLoaded++
        if (imagesLoaded === totalImages) {
          allImagesLoaded()
        }
      }
      $('img').each(function(idx, img) {
        $('<img>')
          .on('load', imageLoaded)
          .attr('src', $(img).attr('src'))
      })

      let start = 0;
      let end = 0;
      setTimeout(()=>{
        const h1 = $("#section1").height();
        const h2 = $("#section2").height();
        const h3 = $("#section3").height();
        const h4 = $("#section4").height();
        const h5 = $("#section5").height();
        const h6 = $("#section6").height();
        const h7 = $("#section7").height();
        start = h1 + h2;
        end = start + h3 + h4 + h5 + h6 + h7;
        console.log("h1 is", h1, ' / h2 is ', h2, ' / start is ', start, ' / end is ', end);
      }, 1000);
      $(window).scroll(()=>{
        const st = $(window).scrollTop();
        // console.log(st);
        switch(true){
          case st < start:
            // console.log("< start, absoulte start");
            $('.sbg').removeAttr('style').css('top', start);
            break;
          case st >= start && st < end:
            // console.log('fixed');
            $('.sbg').removeAttr('style').css({'position': 'fixed', 'top': 0});
            break;
          case st >= end:
            // console.log("> end, absolute end");
            $('.sbg').removeAttr('style').css('top', end);
            break;
          default:
        }
      })
    })
  },
  mounted() {
  },
  methods: {
    init() {}
  }
}
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css?family=Noto+Serif+TC')
@import "src/assets/style/myvar"
*
  font-family: "Noto Serif TC", serif !important
  letter-spacing: 1px
  // Noto Sans CJK TC  粗細Regular 400
  // Noto Serif CJK TC  粗細Regular 400  Bold 700
body, html
  background-color: #004A77
section
  // overflow: visible
  position: relative
.sbg
  width: 100vw
  position: absolute
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .sbg
    height: 100vh
    display: flex
    align-items: flex-end
    .is_mb
      display: none

@media screen and (max-width: $bp-mb)
  .sbg
    .is_pc
      display: none
</style>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Playball&display=swap');
@import '../assets/style/variableColor.scss';

.section,
.section .fp-slide,
.section .fp-tableCell {
  height: auto !important;
}

</style>
