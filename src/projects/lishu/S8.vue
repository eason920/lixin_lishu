<template>
  <div class="relative">
    <section id="sec8">
      <div class="mark"
        data-aos-once="false"
        data-aos="fade-in"
        data-aos-delay="0"
        data-aos-duration="800"
      >
        <img src="./S8/mark.png" />
      </div>
      <div class="title"
        data-aos-once="false"
        data-aos="fade-up"
        data-aos-delay="0"
        data-aos-duration="800"
      >
        <img src="./S8/title.png" />
      </div>
      <div class="sub"
        data-aos-once="false"
        data-aos="fade-up"
        data-aos-delay="0"
        data-aos-duration="800"
      >
        <img src="./S8/sub.png" />
      </div>
    </section>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
@import ./sass/share
#sec8
  & > *
    margin:
      left: auto
      right: auto
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .mark
    width: 40vw
  .title
    width: 20vw
    margin:
      top: 2vw
      bottom: 5vw
  .sub
    width: 42vw

@media screen and (max-width: $bp-mb)
  .mark
    width: 50vw
  .title
    width: 30vw
    margin:
      top: 3vw
      bottom: 9vw
  .sub
    width: 78vw
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
