<template>
  <div
    class="slide-container"
    ref="container"
    @mousedown="mouseDown"
    @mouseenter="mouseEnter"
    @mouseleave="mouseLeave"
    @mousemove.prevent="mouseMove"
    @mouseup="mouseUp"
  >
    <div class="slider" ref="slider">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: "DraggableContainer",
  data() {
    return {
      startX: 0,
      currentX: 0,
      isPressed: false,
    };
  },
  methods: {
    mouseDown(e) {
      this.isPressed = true;
      this.startX = e.offsetX - this.$refs.slider.offsetLeft;
      this.$refs.container.style.cursor = "grabbing";
    },
    mouseEnter(e) {
      this.$refs.container.style.cursor = "grab";
    },
    mouseLeave(e) {
      this.isPressed = false;
      this.$refs.container.style.cursor = "grab";
    },
    mouseUp(e) {
      this.isPressed = false;
      this.$refs.container.style.cursor = "grab";
    },

    mouseMove(e) {
      if (this.isPressed) {
        this.currentX = e.offsetX;
        this.$refs.slider.style.left = `${this.currentX - this.startX}px`;
        this.checkBoundaries();
      }
    },
    checkBoundaries() {
      const containerBoundingRect =
        this.$refs.container.getBoundingClientRect();
      const sliderBoundingRect = this.$refs.slider.getBoundingClientRect();

      const currentSliderLeft = parseInt(this.$refs.slider.style.left);
      console.log(
        containerBoundingRect.right + " - " + sliderBoundingRect.right
      );
      if (currentSliderLeft > 25) {
        this.$refs.slider.style.left = "0px";
      } else if (containerBoundingRect.right > sliderBoundingRect.right) {
        this.$refs.slider.style.left = `-${
          sliderBoundingRect.width - containerBoundingRect.width
        }px`;
      }
    },
  },
};
</script>

<style scoped>
.slide-container {
  height: 400px;
  width: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  overflow: hidden;
}

.slider {
  width: 150%;
  display: flex;
  gap: 36px;
  position: absolute;
  top: 0;
  left: 0;
}
</style>
