<template>
  <transition name="standard-long-fade">
    <section v-if="showLoadingScreen" class="loading-screen">
      <base-image img-src="/src/assets/img/logo.svg"></base-image>
    </section>
  </transition>
</template>
<script>
import BaseImage from "@/components/images/base-image.vue";

export default {
  components: {BaseImage},
  data() {
    return {
      showLoadingScreen: true
    }
  },
  created() {
    setTimeout(() => {
      this.showLoadingScreen = false;
    }, 2500)
  }
}
</script>

<style>
.loading-screen {
  margin: 0;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background-color: #69744E;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 999;

  img {
    animation: rotate 2s ease-in-out infinite;
  }

}

@keyframes rotate {
  0% {
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>