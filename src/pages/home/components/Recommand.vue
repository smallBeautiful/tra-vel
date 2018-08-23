<template>
    <div class="recommand">
        <div class="recommand-title">
            热销推荐
        </div>
        <ul>
            <li 
                class="item border-bottom"
                v-for="item of recommendList"
                :key="item.id"
            >
                <img :src="item.imgUrl" alt="" class="item-img">
                <div class="item-info">
                    <p class="item-title">
                        {{ item.title }}
                    </p>
                    <p class="item-desc">
                        {{ item.desc }}
                    </p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
  
</template>

<script>
export default {
  name: "HomeRecommand",
  props: {
    recommendList: {
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

.item {
    overflow: hidden;
    display: flex;
    height: 1.9rem;

    .item-img {
        width: 1.7rem;
        height: 1.7rem;
        padding: 0.1rem;
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

        .item-button {
            line-height: 0.44rem;
            margin-top: 0.2rem;
            background: #ff9300;
            padding: 0 0.1rem;
            border-radius: 0.06rem;
            color: #fff;
        }
    }
}
</style>
