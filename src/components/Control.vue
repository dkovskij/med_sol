<template>
  <div class="container">
    <div class="description">
      <div class="header">
        Контролируйте показатели своего здоровья
      </div>
      <ul class="list">
        <li v-for="(item, index) in controlList" :key="'control' + index" class="list-item">
          <span>{{ item }}</span>
        </li>
      </ul>
    </div>
    <div v-touch:swipe="swipe" class="carousel">
      <div class="arr-left" @click="changePos('prev')">
        <img src="../assets/img/arr-left.svg" alt="arr-left">
      </div>
      <img v-for="(img, index) in imgList" :key="'img' + index" :src="img.img" :class="['carousel-' + img.class, 'carousel-img']">
      <div class="arr-right" @click="changePos('next')">
        <img src="../assets/img/arr-right.svg" alt="arr-right">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      controlList: ['Артериальное давление', 'Частота сердечных сокращений', 'Сахар в крови', 'Вес', 'Рост', 'Температура', 'Произвольные показатели'],
      imgList: [
        {img: require('../assets/img/group-7-copy.png'), class: -3},
        {img: require('../assets/img/img-2443-copy-2.png'), class: -2},
        {img: require('../assets/img/group-7-copy-2.png'), class: -1},
        {img: require('../assets/img/group-7.png'), class: 0},
        {img: require('../assets/img/group-7-copy-4.png'), class: 1},
        {img: require('../assets/img/group-7-copy-5.png'), class: 2},
        {img: require('../assets/img/group-7-copy-6.png'), class: 3},
      ]
    }
  },
  methods: {
    changePos(direction) {
    if (direction === 'prev') {
      if (this.imgList[0].class === -6) {
          return
        }
      for (let i = 0; i < this.imgList.length; i++) {
        this.imgList[i].class--
      }
    } else if (direction === 'next') {
      if (this.imgList[6].class === 6) {
          return
        }
      for (let i = 0; i < this.imgList.length; i++) {
        this.imgList[i].class++
      }
    }
  },
  swipe(direction) {
    if (direction === 'right') {
      this.changePos('next')
    } else {
      this.changePos('prev')
    }
  }
  },
}
</script>

<style lang="scss" scoped>
  @import '@/styles/control.scss';
  @media screen and (max-width: 1080px) {
    .container {
      grid-template-columns: 1fr;
      justify-items: center;
    }
    .description {
      .header {
        margin-top: 50px;
      }
    }
  }
  @media screen and (max-width: 1024px) {
    @import '@/styles/small/sm-control';
  }
  @media screen and (max-width: 768px) {
    @import '@/styles/xs/xs-control';
  }
</style>
