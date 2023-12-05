<template>
  <div ref="lottieContainer" class="lottie-container"></div>
</template>

<script>
9;
import lottie from "lottie-web";
export default {
  props: {
    Path: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      animation: null,
    };
  },
  watch: {
    Path: {
      immediate: true,
      handler(value) {
        if (this.animation) {
          lottie.destroy();
        }

        this.animation = lottie.loadAnimation({
          container: this.$refs.lottieContainer,
          renderer: "svg",
          loop: true,
          autoplay: true,
          path: value,
        });
      },
    },
  },
};
</script>

<style>
.lottie-container {
  zoom: 50%;
}
</style>
