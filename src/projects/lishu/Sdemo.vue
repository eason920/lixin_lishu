<template>
  <div class="relative">
    <section id="sec1"></section>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
@import ./sass/share

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
      isTablet
    }
  },

  methods: {},

  created() {},

  mounted() {},

  computed: {}
}
</script>
