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
        </div>
      </div>
    </div>
    <BubleRound
      class="buble1"
      :title="title"
      :text="text"
      :plusButtonVisible="true"
    >
    </BubleRound>
  </div>
</template>

<script>
import "@/assets/css/font.css";

import BubleRound from "./components/BubleRound.vue";

export default {
  name: "App",
  components: {
    BubleRound,
  },
  data() {
    return {
      title: "Phyto-pharmaceutical",
      text:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco",
    };
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
  top: 351px;
  left: 200px;
}

</style>
