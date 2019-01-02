<template>
  <div>
    <button @click="toggle">Toggle</button>
    <SlideDownTransition>
      <div v-if="show" class="box">
        <p v-for="c in count" :key="c">{{ text }}</p>
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
      count: 5,
      text: 'Some text',
    };
  },

  methods: {
    toggle() {
      this.show = !this.show;

      if (!this.show) {
        this.count = Math.floor(Math.random() * 5) + 1;
      }
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
