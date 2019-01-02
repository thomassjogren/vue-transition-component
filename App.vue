<template>
  <div>
    <button @click="toggle">Toggle</button>
    <SlideDownTransition>
      <div v-if="show" class="box">
        <p>{{ text }}</p>
        <p>{{ text }}</p>
        <p>{{ text }}</p>
        <p>{{ text }}</p>
      </div>
    </SlideDownTransition>
  </div>
</template>

<script>
import SlideDownTransition from './SlideDownTransition';

export default {
  components: { SlideDownTransition },

  data() {
    return {
      show: false,
      text: 'Some text',
    };
  },

  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
};
</script>

<style>
.box {
  background-color: #eee;
  overflow: hidden;
  position: relative;
  width: 200px;
  will-change: height;
  transform: translateZ(0);
  backface-visibility: hidden;
  perspective: 1000px;
}
</style>
