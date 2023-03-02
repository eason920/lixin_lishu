<template>
  <div class="relative">
    <section id="sec2">
      <div
        data-aos-once="false"
        data-aos="fade-up"
        data-aos-delay="0"
        data-aos-duration="1400"
      >
        <img src="./S2/map.jpg" />
      </div>
    </section>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"

@media screen and (min-width: $bp-pc)
  #sec2
    padding:
      top: 1vw
      bottom: 9.5vw
    img
      // height: 90vh
      width: 80vw
    .wave1
      position: absolute
      left: 0
      top: -10vh

@media screen and (max-width: $bp-mb)
  #sec2
    background:
      color: #000
    img
      width: 100%
</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'

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

  mounted() {},

  computed: {}
}
</script>
