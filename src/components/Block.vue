<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click Here Now</div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  updated() {
    console.log('updated');
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log(this.reactionTime);
      this.$emit('end', this.reactionTime);
    },
  },
};
</script>

<style>
.block {
  text-align: center;
  background: green;
  color: lime;
  width: 500px;
}
</style>
