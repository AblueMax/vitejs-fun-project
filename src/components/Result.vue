<template>
  <p>Reaction Time = {{ score }} ms</p>
  <p>{{rank}}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null
    }
  },
  mounted() {
    if(this.score < 400) {
      this.rank = 1;
    } else {
      this.rank = '&#128517;';
    }
  }
}
</script>