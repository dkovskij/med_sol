<template>
  <div class="wrap">
    <div class="container">
      <div class="description">
        <h1>
          Все данные о вашем здоровье в одном приложении
        </h1>
        <div class="subdescr">
          Универсальная медицинская карта и сервис для дистанционного сопровождения пациентов, которая решает следующие проблемы:
        </div>
        <div class="advantages">
          <div v-for="(item, index) in advantages" :key="'adv' + index" :style="'background: url(' + item.background + ') no-repeat;'" class="advantage">
            {{ item.text }}
          </div>
        </div>
        <div class="mobile-stores">
          <div>
            <img src="../assets/img/play-store.svg" alt="play-store">
          </div>
          <div>
            <img src="../assets/img/app-store.svg" alt="app-store">
          </div>
        </div>
      </div>
      <div class="carousel">
        <div class="carousel-wrap">
          <div :class="[activeButton === 'ios' ? 'active' : '', 'first']" @click="setActiveButton('ios')">
            <img src="../assets/img/mob-copy-5.png" srcset="../assets/img/mob-copy-5@2x.png 2x, ../assets/img/mob-copy-5@3x.png 3x" class="img">
          </div>
          <div :class="[activeButton === 'android' ? 'active' : '', 'second']" @click="setActiveButton('android')">
            <img src="../assets/img/mob-copy-8.png" srcset="../assets/img/mob-copy-8@2x.png 2x, ../assets/img/mob-copy-8@3x.png 3x" class="img">
          </div>
        </div>
        <div class="buttons">
          <div :class="[activeButton === 'ios' ? 'active-button' : '', 'ios']" @click="setActiveButton('ios')">
          </div>
          <div :class="[activeButton === 'android' ? 'active-button' : '', 'android']" @click="setActiveButton('android')">
          </div>
          <div class="button-name" @click="setActiveButton('ios')">
            iOS
          </div>
          <div class="button-name" @click="setActiveButton('android')">
            Android
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      advantages: [
        {text: 'Все необходимое в одном месте', background: require('../assets/img/adv_phone.svg')},
        {text: 'Разработано врачами', background: require('../assets/img/adv_steto.svg')},
        {text: 'Безопасность данных', background: require('../assets/img/adv_lock.svg')},
        {text: 'Бесплатное приложение', background: require('../assets/img/adv_rub.svg')}
      ],
      activeButton: 'ios'
    }
  },
  methods: {
    setActiveButton(button) {
      this.activeButton = button
    }
  },
}
</script>

<style scoped lang="scss">
  @import '@/styles/first-block';
  @media screen and (max-width: 1280px) {
    .description {
      grid-column: 1 / 3;
    }
    .carousel {
      grid-column: 1 / 3;
      .carousel-wrap {
        height: 540px;
        .first {
          left: 30%;
        }
        .second {
          left: 50%;
        }
      }
    }
  }
  @media screen and (max-width: 1024px) {
    @import '@/styles/small/sm-first-block.scss';
  }
  @media screen and (max-width: 768px) {
    @import '@/styles/xs/xs-first-block';
  }
</style>
