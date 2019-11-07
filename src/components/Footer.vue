<template>
  <div class="wrap">
    <footer>
      <div class="logo">
        <img src="../assets/img/med_sol_gray.svg" alt="logo">
      </div>
      <div class="copyright">
        <p>
          EN / RU
        </p>
        <p>
          Моё Здоровье
        </p>
        <p>
          2016–2019 © ООО «МИР»
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '@/styles/footer.scss';
@media screen and (max-width: 1024px) {
  @import '@/styles/small/sm-footer';
}
</style>
