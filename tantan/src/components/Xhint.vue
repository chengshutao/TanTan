<template>
  <!-- <van-popup v-model="show" position="top" :overlay="true" :overlayStyle="hint" @click="open">内容</van-popup> -->
  <!-- <div> -->
  <!-- <div data-v-1702377f class="van-popup van-popup--top" style="z-index: 2001;" @click="open">内容</div> -->
  <div class="van-overlay" :style="hint">开发中</div>
  <!-- </div> -->
</template>
<script>
import bus from "../bus.js";
export default {
  //   props: ["hint"],
  data() {
    return {
      show: true,
      hint: {
        height: 0,
        zIndex: 2000,
        fontSize: "0.533333rem",
        color: "#fff",
        lineHeight: "1.6rem",
        paddingLeft: "0.666667rem"
      }
    };
  },
  methods: {
    open() {
      setTimeout(() => {
        this.hint.height = "1.6rem";
      }, 200);
      setTimeout(() => {
        this.hint.height = 0;
      }, 2000);
    }
  },
  created() {
    bus.$on("showhint", () => {
      this.open();
    });
  }
};
</script>
<style scoped>
/* .van-popup {
  background-color: transparent;
  font-size: 0.533333rem;
  color: #fff;
  line-height: 1.6rem;
  padding-left: 0.666667rem;
} */

.van-overlay {
  transition: all 0.5s;
  overflow: hidden;
}
</style>
