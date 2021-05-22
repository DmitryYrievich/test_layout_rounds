<template>
  <div class="app pa" id="app">
    <div class="main-container pa" id="main-container">
      <div class="tab-title pa" id="tab-title">
        <p class="tab-title-text pa">
          <strong>Phyto = Phyto?</strong> Herbal products are not equal
        </p>
      </div>
      <div class="content-box pa">
        <div class="content-box-left pa">
          <p class="box-title box-title1 pa">
            Phytopharmaceutical products<br /><span class="wite-text"
              >on the market.</span
            >
          </p>
          <BubleRound
            class="buble1"
            :title="title1"
            :text="text1"
            :plusButtonVisible="true"
            :packsSrc="packsSrc"
          >
          </BubleRound>
        </div>
        <div class="content-box-right pa">
          <p class="box-title box-title2 pa">
            Categories of herbal products<br /><span class="wite-text"
              >on the market.</span
            >
          </p>
          <transition>
            <div class="buble-box pa" refs="bubleBox">
              <BubleRound
                @click="toggleItem(index)"
                v-for="(buble, index) in 5"
                :key="index"
                :class="[
                  `buble${index + 2}`,
                  { activeOnPage: activeElement === index },
                ]"
                :title="title1"
                :text="text1"
              >
                {{ buble }}
              </BubleRound>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "@/assets/css/font.css";

import pack1 from "./assets/images/packshot01@2x.png";
import pack2 from "./assets/images/packshot02@2x.png";
import pack3 from "./assets/images/packshot03@2x.png";
import pack4 from "./assets/images/packshot04@2x.png";
import pack5 from "./assets/images/packshot05@2x.png";
import pack6 from "./assets/images/packshot06@2x.png";
import pack7 from "./assets/images/packshot07@2x.png";

import BubleRound from "./components/BubleRound.vue";

export default {
  name: "App",
  components: {
    BubleRound,
  },
  data() {
    return {
      activeElement: null,
      title1: "Phyto-pharmaceutical",
      text1:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco",
      packsSrc: [pack1, pack2, pack3, pack4, pack5, pack6, pack7],
    };
  },
  mounted() {
    console.log(this.$refs.buble);
  },
  methods: {
    toggleItem(index) {
      this.activeElement = index;
      console.log(index);
    },
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  width: 1024px;
  height: 768px;
}
p {
  margin: 0;
}
.pa {
  position: absolute;
  top: 0;
  left: 0;
}
#app {
  font-family: mega;
}
.app {
  width: 1024px;
  height: 768px;
  background-image: url("./assets/images/bg.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
.main-container {
  width: 1024px;
  height: 652px;
  top: 54px;
  bottom: 62px;
  background: rgba(0, 0, 0, 0.5);
}
.tab-title {
  width: 952px;
  height: 79px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 11px 11px 0;
  top: 20px;
  left: 41px;
}
.tab-title-text {
  font-weight: 300;
  font-size: 34px;
  color: #00457d;
  top: 20px;
  left: 136px;
}
.tab-title-text strong {
  font-weight: 600;
}
.content-box {
  width: 900px;
  height: 552px;
  top: 99px;
  left: 79px;
}
.content-box-left {
  width: 433px;
  height: 495px;
  top: 36px;
  border-right: 1px solid #ecebf1;
}
.box-title {
  font-size: 24px;
  font-weight: 700;
  text-align: center;
  color: #97bf0d;
  letter-spacing: 0.6px;
  line-height: 1;
}
.box-title1 {
  top: 15px;
  left: 23px;
}
.wite-text {
  color: #ffffff;
  font-size: 20px;
}
.buble1 {
  top: 162px;
  left: 121px;
}
#packs-images1 {
  left: 72px;
  top: 2px;
}
#packs-images2 {
  left: 256px;
  top: 2px;
}
#packs-images3 {
  left: 322px;
  top: 122px;
}
#packs-images4 {
  left: 292px;
  top: 242px;
}
#packs-images5 {
  left: 169px;
  top: 284px;
}
#packs-images6 {
  left: 33px;
  top: 242px;
}
#packs-images7 {
  left: 7px;
  top: 112px;
}
.content-box-right {
  width: 450px;
  height: 495px;
  top: 36px;
  left: 448px;
}
.box-title2 {
  top: 15px;
  left: 53px;
}
.buble2 {
  top: 7px;
  left: 4px;
}
.buble3 {
  top: 66px;
  left: 149px;
}
.buble4 {
  top: 7px;
  left: 295px;
}
.buble5 {
  top: 177px;
  left: 33px;
}
.buble6 {
  top: 177px;
  left: 264px;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 6.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.buble-box {
  width: 450px;
  height: 337px;
  top: 103px;
}
.active-on-page {
  scale: 2;
}
</style>
