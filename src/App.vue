<template>
  <div id="app">
    <div class="container">
      <div class="first-block">
        <Header></Header>
        <FirstBlock></FirstBlock>
        <SecondBlock></SecondBlock>
        <Footer></Footer>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header'
import FirstBlock from '@/components/FirstBlock'
import SecondBlock from '@/components/SecondBlock'
import Footer from '@/components/Footer'

export default {
  components: {
    Header,
    FirstBlock,
    SecondBlock,
    Footer
  }
}
</script>

<style lang="scss">
@import '@/styles/main';
@media screen and (max-width: 768px) {
  @import '@/styles/small/sm-main.scss';
}
@media screen and (max-width: 360px) {
  @import '@/styles/xs/xs-main';
}
</style>
