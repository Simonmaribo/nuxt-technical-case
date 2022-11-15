<template>
  <div
    class="slider"
    ref="slider"
    @mousedown="mouseDown"
    @mouseenter="mouseEnter"
    @mouseleave="mouseLeave"
    @mousemove.prevent="mouseMove"
    @mouseup="mouseUp"
  >
    <slot />
  </div>
</template>

<script>
export default {
  name: "DraggableContainer",
  data() {
    return {
      startX: 0,
      scrollLeft: 0,
      isPressed: false,
    };
  },
  methods: {
    mouseDown(e) {
      this.isPressed = true;
      this.startX = e.pageX;
      this.scrollLeft = this.$refs.slider.scrollLeft;
      this.$refs.slider.style.cursor = "grabbing";
    },
    mouseEnter(e) {
      this.$refs.slider.style.cursor = "grab";
    },
    mouseLeave(e) {
      this.isPressed = false;
      this.$refs.slider.style.cursor = "grab";
    },
    mouseUp(e) {
      this.isPressed = false;
      this.$refs.slider.style.cursor = "grab";
    },

    mouseMove(e) {
      if (this.isPressed) {
        const distanceToStart = e.pageX - this.startX;
        console.log(distanceToStart);

        this.$refs.slider.scrollTo({
          left: this.scrollLeft - distanceToStart,
          // distanceToStart falder (negativ) når du trækker til højre
          // distanceToStart stiger (positiv) når du trækker til venstre

          behavior: "instant",
        });
      }
    },
  },
};
</script>

<style scoped>
.slider {
  overflow: scroll;
  display: flex;
  gap: 10px;
  cursor: grab;
}
</style>
