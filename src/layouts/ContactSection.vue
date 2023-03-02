<template>
  <div class="contact" id="contact">
    <Order />
    <HouseInfo />
  </div>
</template>
<style lang="sass" scoped>
@import "src/assets/style/myvar"
#contact
  background: #000
@media screen and (min-width: $bp-pc)
  #contact
    padding-top: 200px

@media screen and (max-width: $bp-mb)
  #contact
    padding-top: 80px
</style>

<script>
import Order from '@/components/Order.vue'
import HouseInfo from '@/components/HouseInfo.vue'

export default {
  name: 'contactSection',
  components: {
    Order,
    HouseInfo
  },

  methods: {}
}
</script>
