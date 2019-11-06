<template>
  <div class="wrap header-wrap">
    <header>
      <div class="logo">
        <img src="../assets/img/my-health-rus.svg" alt="logo">
      </div>
      <div class="stores">
        <div class="play-store">
        <img src="../assets/img/play-store.svg" alt="play-store">
      </div>
      <div class="app-store">
        <img src="../assets/img/app-store.svg" alt="app-store">
      </div>
      </div>
      <div class="med-sol">
        <img src="../assets/img/med_sol.svg" alt="my-health">
      </div>
      <div class="hamburger">
        <img src="../assets/img/hamb.svg" alt="hamburger">
      </div>
    </header>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
@import '@/styles/header';
@media screen and (max-width: 768px) {
  @import '@/styles/small/sm-header.scss';
}
@media screen and (max-width: 360px) {
  @import '@/styles/xs/xs-header';
}
</style>
