<template>
    <div class="water">
        <div class="anwater">
            <img src="./all/w.png" />
            <img src="./all/w.png" />
        </div>
    </div>
</template>

<style lang="sass" scoped>
@keyframes aniWater
  0%
    transform: translateX(-50%)
  20%
    transform: translateX(-40%)skewX(5deg)scaleY(.8)
  40%
    transform: translateX(-30%)
  60%
    transform: translateX(-20%)
  80%
    transform: translateX(-10%)skewX(-5deg)scaleY(.8)
  100%
    transform: translateX(0)

.anwater
  width: 200%
  animation: aniWater 10s linear infinite 
  img
    width: 50%
</style>
