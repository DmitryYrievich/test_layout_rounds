<template>
  <div class="buble-wrapp pa" refs="buble">
    <div
      class="buble pa"
      :class="{ pulse: pulseAnimation, active: isActive }"
      @click="isActive = !isActive"
    >
      <p class="buble-title">{{ title }}</p>
      <p class="buble-text">{{ text }}</p>
      <button
        class="packs-open pa"
        v-if="plusButtonVisible"
        :class="{ swing: isShownContent }"
        @click.stop.prevent="isShownContent = !isShownContent"
      >
        <img
          src="../assets/images/plus@2x.png"
          alt="plus"
          class="packs-open-img"
        />
      </button>
    </div>
    <transition name="fade">
      <div class="packs-collection-container pa" v-if="isShownContent">
        <img
          v-for="(pack, index) in packsSrc"
          :key="index"
          :src="`${pack}`"
          alt="plus"
          class="packs-images pa"
          :id="`packs-images${index + 1}`"
        />
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "BubleRound",
  props: {
    title: String,
    text: String,
    pulseAnimation: {
      type: Boolean,
      default: true,
    },
    plusButtonVisible: {
      type: Boolean,
      default: false,
    },
    packsSrc: {
      type: Array,
      default: () => {
        return [];
      },
    },
  },
  data() {
    return {
      isShownContent: false,
      isActive: false,
    };
  },
  mounted() {
    console.log(this.$refs.buble);
  },
};
</script>


<style scoped>
.buble-wrapp {
  width: 150px;
  height: 150px;
}
.buble {
  width: 150px;
  height: 150px;
  box-sizing: border-box;
  border-radius: 50%;
  border: 8px solid #ffffff;
  background: transparent;
  font-family: mega;
  padding: 10px 5px;
  transition: 0.3s transform;
}
.buble.pulse {
  animation: pulse 2s infinite;
}
.buble.active {
  transform: scale3d(1.5, 1.5, 1.5);
  background: rgba(0, 0, 0, 0.7);
  border-radius: 100%;
  animation: none;
}
.buble-title {
  font-size: 16px;
  text-align: center;
  color: #97bf0d;
  font-weight: 600;
  line-height: 1.2;
  padding-bottom: 2px;
}
.buble-text {
  font-size: 8px;
  text-align: center;
  color: #ffffff;
  font-weight: 600;
  line-height: 1.2;
}
@keyframes pulse {
  0% {
    -moz-box-shadow: 0 0 0 0 rgba(245, 244, 241, 0.877);
    box-shadow: 0 0 0 0 rgba(245, 244, 241, 0.877);
  }
  70% {
    -moz-box-shadow: 0 0 0 10px rgba(204, 169, 44, 0);
    box-shadow: 0 0 0 10px rgba(204, 169, 44, 0);
  }
  100% {
    -moz-box-shadow: 0 0 0 0 rgba(204, 169, 44, 0);
    box-shadow: 0 0 0 0 rgba(204, 169, 44, 0);
  }
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.packs-open-img,
.packs-open {
  width: 25px;
  height: 25px;
}
.packs-open {
  padding: 0;
  background: transparent;
  border: 0;
  top: 2px;
  left: 101px;
  z-index: 2;
}
.packs-open.swing {
  transform: rotate(-45deg);
}
.packs-collection-container {
  width: 411px;
  height: 355px;
  top: -94px;
  left: -129px;
  pointer-events: none;
}
.packs-images {
  width: 81px;
  height: 72px;
}
</style>
