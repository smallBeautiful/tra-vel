<template>
    <div class="recommand">
        <div class="recommand-title">
            周末去哪
        </div>
        <ul>
            <li 
                class="item border-bottom"
                v-for="item of weekendList"
                :key="item.id"
            >
                <div class="item-img-wrapper">
                    <img :src="item.imgUrl" alt="" class="item-img">
                </div>
                <div class="item-info">
                    <p class="item-title">
                        {{ item.title }}
                    </p>
                    <p class="item-desc">
                        {{ item.desc }}
                    </p>
                </div>
            </li>
        </ul>
    </div>
  
</template>

<script>
export default {
  name: "Weekend",
  props: {
    weekendList: {
      type: Array
    }
  },
  data() {
    return {};
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='stylus' scoped>
@import '~styles/mixins.styl';

.recommand-title {
    line-height: 0.8rem;
    background: #eee;
    text-indent: 0.2rem;
}

.item-img-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 33.9%;

    .item-img {
        width: 100%;
    }
}

.item-info {
    flex: 1;
    padding: 0.1rem;
    min-width: 0;

    .item-title {
        line-height: 0.54rem;
        font-size: 0.32rem;
        ellipsis();
    }

    .item-desc {
        line-height: 0.4rem;
        font-size: 0.28rem;
        color: #ccc;
        ellipsis();
    }
}
</style>
