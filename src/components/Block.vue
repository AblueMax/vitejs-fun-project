<template>
  <div class="block" v-if="showBlock">Click Here Now</div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false,
    };
  },
  mounted() {
    console.log('mounted');
    setTimeout(() => {
      this.showBlock = true;
    }, this.delay);
  },
  updated() {
    console.log('updated');
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
