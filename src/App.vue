<template>
  <div id="app">
    <div class="container">
      <div class="first-block">
        <Header></Header>
        <FirstBlock></FirstBlock>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header'
import FirstBlock from '@/components/FirstBlock'

export default {
  components: {
    Header,
    FirstBlock
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Open+Sans&display=swap');
@import '@/styles/main';
</style>
