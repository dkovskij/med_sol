<template>
  <div class="opportunities-container">
    <div class="header">
      Возможности приложения
    </div>
    <ul class="oppo-list">
      <li v-for="(item, index) in oppos" :key="'oppo' + index" class="list-item">
        <div class="text" :style="'background: url(' + item.bg + ') no-repeat'" >
          {{ item.text }}
          <div class="soon" v-if="item.soon">
            Скоро
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      oppos: [
        {text: 'Контроль показателей своего здоровья', bg: require('../assets/img/group-28.svg'), soon: false},
        {text: 'Хранение медицинских документов', bg: require('../assets/img/group-33.svg'), soon: false},
        {text: 'Календарь менструального цикла', bg: require('../assets/img/group-30.svg'), soon: false},
        {text: 'Актуальные новости', bg: require('../assets/img/group-333.svg'), soon: false},
        {text: 'Создание курсов прием лекарств', bg: require('../assets/img/group-300.svg'), soon: false},
        {text: 'Создание напоминаний', bg: require('../assets/img/group-34.svg'), soon: false},
        {text: 'Дневник течения беременности', bg: require('../assets/img/group-31.svg'), soon: false},
        {text: 'Консультации врачей онлайн', bg: require('../assets/img/group-288.svg'), soon: true},
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/oppo.scss';
@media screen and (max-width: 1040px) {
  .oppo-list {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media screen and (max-width: 1024px) {
  @import '@/styles/small/sm-opportunities';
}
@media screen and (max-width: 768px) {
  @import '@/styles/xs/xs-opportunities';
}
</style>
