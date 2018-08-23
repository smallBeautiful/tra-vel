<template>
  <div >
      <home-header :city='city'></home-header>
      <home-swiper :list='swiperList'></home-swiper>
      <icons :iconList='iconList'></icons>
      <home-recommand :recommendList='recommendList'></home-recommand>
      <home-weekend :weekendList='weekendList'></home-weekend>
  </div>
</template>

<script>
import HomeHeader from "./components/Header";
import HomeSwiper from "./components/HomeSwiper";
import Icons from "./components/Icons";
import HomeRecommand from "./components/Recommand";
import HomeWeekend from "./components/Weekend";
import axios from "axios";
export default {
  name: "Home",
  components: {
    HomeHeader,
    HomeSwiper,
    Icons,
    HomeRecommand,
    HomeWeekend
  },
  data() {
    return {
      city: "上海",
      iconList: [],
      recommendList: [],
      swiperList: [],
      weekendList: []
    };
  },
  mounted() {
    this.getHomeInfo();
  },
  methods: {
    getHomeInfo() {
      axios.get("./api/index.json").then(this.getHomeDataSucc);
    },
    getHomeDataSucc(data) {
      if (data.data.ret && data.data) {
        data = data.data.data;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
        console.log(this.swiperList);
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
