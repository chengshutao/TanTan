<template>
  <main>
    <div class="headimg">
      <img src="../assets/a.jpg" alt>
      <span @click="showhint"></span>
    </div>
    <div class="personaltitle">
      <h2 v-text="title"></h2>
      <p class="tag">
        <i class="iconfont icon-nan"></i>
        <span>23</span>
      </p>
      <p class="tag mar" style="background:#d3332e;">水瓶座</p>
      <div class="perstate">现在活跃</div>
    </div>
    <div class="main_box">
      <section class="van-doc-demo-block">
        <!-- <h2 class="van-doc-demo-block__title">基础用法</h2> -->
        <div class="van-cell-group van-hairline--top-bottom">
          <div class="van-cell member" @click="showhint">
            <div class="van-cell__title">
              <span>未开通会员</span>
            </div>
            <div class="van-cell__value">
              <span class="m_rigt">查看特权</span>
            </div>
          </div>
          <div class="van-cell like">
            <div class="van-cell__title">
              <span>
                <b>4</b>人喜欢了你
              </span>
            </div>
            <div class="van-cell__value">
              <span @click="showhint">谁喜欢我？</span>
            </div>
          </div>
        </div>
      </section>
      <section class="van-doc-demo-block">
        <h2 class="van-doc-demo-block__title">我的信息</h2>
        <div class="van-cell-group van-hairline--top-bottom">
          <div class="van-cell" v-for="(i,index) in mymes" :key="index">
            <div class="van-cell__title">
              <span v-text="i.title"></span>
            </div>
            <div class="van-cell__value mymes_r">
              <span class="mymes_rtext" v-text="i.content"></span>
            </div>
          </div>
        </div>
      </section>
      <section class="van-doc-demo-block">
        <h2 class="van-doc-demo-block__title">我的兴趣</h2>
        <div class="van-cell-group van-hairline--top-bottom">
          <div class="van-cell" v-for="(i,index) in myinter" :key="index">
            <div class="van-cell__title">
              <van-icon :name="i.icon" :color="i.backcol" size=" .533333rem"/>
            </div>
            <div class="van-cell__value myinter_r">
              <!-- 有内容为  class="have" :style="`backgroundColor:${i.backcol};color:#fff;`" -->
              <span class="mymes_rtext">
                <b v-text="i.content"></b>
              </span>
            </div>
          </div>
        </div>
      </section>

      <section class="van-doc-demo-block">
        <h2 class="van-doc-demo-block__title">我的问答</h2>
        <div class="van-cell-group van-hairline--top-bottom">
          <div class="van-cell" v-for="(i,index) in myque" :key="index">
            <div class="van-cell__title myque_r">
              <span v-text="i.questions"></span>
              <div class="van-cell__label" v-text="i.answers"></div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </main>
</template>
<script>
import bus from "../bus.js";
export default {
  data() {
    return {
      title: "吹挚友",
      mymes: [
        { title: "星座", content: "水瓶座" },
        { title: "行业", content: "IT/互联网/通信" },
        { title: "星座", content: "水瓶座" }
      ],
      myinter: [
        { icon: "fire", content: "我喜欢的运动", backcol: "#439641" },
        { icon: "service", content: "我喜欢的歌手", backcol: "#1232c4" },
        { icon: "like", content: "我喜欢的食物", backcol: "#c7604a" },
        {
          icon: "browsing-history",
          content: "我喜欢的电影",
          backcol: "#51507a"
        },
        { icon: "column", content: "我喜欢的书和漫画", backcol: "#d6ae42" },
        { icon: "invition", content: "我的旅行足迹", backcol: "#74a1c2" }
      ],
      myque: [
        {
          questions: "如果有钱有时间，最想去做什么？",
          answers: "旅游"
        }
      ]
    };
  },
  methods: {
    showhint() {
      // console.log(1);
      bus.$emit("showhint");
    }
  }
};
</script>
<style>
main {
  margin-top: 1.066667rem;
  width: 100%;
}
.headimg {
  position: relative;
}
.headimg img {
  width: 100%;
  height: 10rem;
}
.headimg span {
  position: absolute;
  width: 0.666667rem;
  height: 0.666667rem;
  display: block;
  right: 0.413333rem;
  top: 1.04rem;
  background: url(../assets/headerapprove.png) no-repeat;
  background-size: contain;
}
.personaltitle {
  padding: 0.373333rem 0.453333rem;
}
.personaltitle h2 {
  font-size: 0.48rem;
  font-weight: bold;
  color: #4a4a4a;
}
.tag {
  text-align: center;
  width: 1.173333rem;
  height: 0.426667rem;
  border-radius: 0.133333rem;
  display: inline-block;
  background: #8fb7ed;
  padding: 0 0.186667rem;
  margin-top: 0.186667rem;
  color: #fff;
}
.mymes_r b {
  padding: 0.2rem;
}

.have {
  border-radius: 0.133333rem;
}

.tag span,
.tag i {
  line-height: 0.426667rem;
  font-size: 0.266667rem;
  margin-left: 0.16rem;
}
.tag i {
  margin: 0;
}
.mar {
  margin-left: 0.106667rem;
}

.perstate {
  font-size: 0.32rem;
  color: #a6a6a6;
  margin-top: 0.213333rem;
}
.main_box .member {
  height: 1.573333rem;
  background: #fefaed url(../assets/permember.jpg) no-repeat 0.32rem 0.48rem;
  padding-left: 1.466667rem;
  /* color: #424242; */
  font-weight: bold;
  background-size: 0.64rem;
}
main .main_box .member::after {
  content: "";
  left: 0;
}

.van-cell__title {
  align-self: center;
  color: #9b9b9b;
}
main .mymes_r {
  flex: 2;
  text-align: left;
}
main .myinter_r {
  flex: 8;
  text-align: left;
}
.mymes_rtext {
  color: #424242;
}
.mymes_rtext b {
  font-weight: normal;
  padding: 0.186667rem;
}
.m_rigt {
  color: #c85640;
  line-height: 1.066667rem;
}
.main_box .like {
  background: url(../assets/perlike.jpg) no-repeat 0.426667rem 0.48rem;
  background-size: 0.426667rem 0.373333rem;
  padding-left: 1.466667rem;
  color: #999999;
}
.main_box .like b {
  color: #c85640;
}
main .myque_r span {
  color: #424242;
}
.main_box .like .van-cell__value span {
  /* display: inline-block; */
  padding: 0.186667rem;
  background: #f5f5f0;
  border-radius: 0.133333rem;
}
.van-doc-demo-block__title {
  background: #f5f5f1;
  padding-left: 0.453333rem;
  color: #9b9b9b;
  font-size: 0.386667rem;
  padding-top: 0.68rem;
  padding-bottom: 0.32rem;
}
</style>
