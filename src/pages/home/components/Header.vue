<template>
  <div class="header"> 
      <div class="header-left">
          <span class="iconfont">&#xe624;</span>
      </div>
      <div class="header-input">
          <span class="iconfont">&#xe632;</span>
          输入城市景点
      </div>
      <router-link to='/city'>
        <div class="header-right">
          {{ city }}
          <span class="iconfont arrow-icon">&#xe64a;</span>
        </div>
      </router-link>

  </div>
</template>

<script>
export default {
  props: {
    city: String
  },
  name: "HomeHeader",
  data() {
    return {};
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='stylus' scoped>
@import '~styles/varibles.styl';

.header {
    height: 0.86rem;
    line-height: 0.86rem;
    display: flex;
    background: $bgColor;
    color: #fff;

    .header-left {
        width: 0.64rem;
        float: left;
        text-align: center;
        font-size: 0.4rem;
    }

    .header-input {
        flex: 1;
        height: 0.64rem;
        line-height: 0.64rem;
        padding-left: 0.2rem;
        margin-left: 0.2rem;
        margin-top: 0.12rem;
        background: #fff;
        border-radius: 0.1rem;
        color: #ccc;
    }

    .header-right {
        width: 1.24rem;
        float: right;
        text-align: center;
        color: #fff;

        .arrow-icon {
            font-size: 0.24rem;
        }
    }
}
</style>
