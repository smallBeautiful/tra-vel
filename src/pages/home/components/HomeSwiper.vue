<template>
  <div class="container">
    <swiper :options="swiperOption" v-if='showSwiper'>
      <swiper-slide 
        class="swiper-image" 
        v-for="item of list" :key='item.id'
      >
        <img :src="item.imgUrl">
        {{item.url}}
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
  
</template>

<script>
export default {
  name: "HomeSwiper",
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: true
      }
    };
  },
  computed: {
    showSwiper() {
      return this.list.length;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='stylus' scoped>
.container >>> .swiper-pagination-bullet-active {
  background: #fff !important;
}

.container {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 31.25%;

  .swiper-image {
    img {
      width: 100%;
    }
  }
}
</style>
