<template>
  <div class="wrap">
    <Opportunities></Opportunities>
    <Control></Control>
  </div>
</template>

<script>
import Opportunities from '@/components/Opportunities'
import Control from '@/components/Control'

export default {
  components: {
    Opportunities,
    Control
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/second-block.scss';
@media screen and (max-width: 1919px) {
  @import '@/styles/small/sm-second-block';
}
@media screen and (max-width: 767px) {
  @import '@/styles/xs/xs-second-block';
}
</style>
