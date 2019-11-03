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
    <div class="carousel">
      <div class="arr-left" @click="changePos('prev')">
        <img src="../assets/img/arr-left.svg" alt="arr-left">
      </div>
      <img v-for="(img, index) in imgList" :key="'img' + index" :ref="'img' + index" :src="img.img" :class="['carousel-' + img.class, 'carousel-img']">
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
  mounted() {
    console.log(this.$refs) // eslint-disable-line
    // for (let key in this.$refs) {
    //   switch (key) {
    //     case 'img0':
    //       this.$refs[key][0].classList.add('carousel--3')
    //       break
    //     case 'img1':
    //       this.$refs[key][0].classList.add('carousel--2')
    //       break
    //     case 'img2':
    //       this.$refs[key][0].classList.add('carousel--1')
    //       break
    //     case 'img3':
    //       this.$refs[key][0].classList.add('carousel-0')
    //       break
    //     case 'img4':
    //       this.$refs[key][0].classList.add('carousel-1')
    //       break
    //     case 'img5':
    //       this.$refs[key][0].classList.add('carousel-2')
    //       break
    //     case 'img6':
    //       this.$refs[key][0].classList.add('carousel-3')
    //       break
    //   }
    // }
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
  }
  },
}
</script>

<style lang="scss" scoped>
  @import '@/styles/control.scss';
</style>
