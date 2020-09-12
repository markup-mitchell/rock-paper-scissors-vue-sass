<template>
  <div
    class="btn-wrapper"
    v-bind:class="[
      { rock: value === 'rock' },
      { paper: value === 'paper' },
      { scissors: value === 'scissors' }
    ]"
  >
    <button class="btn"></button>
  </div>
</template>

<style lang="scss" scoped>
@import '../styles/styles.scss';
.btn-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 130px;
  height: 130px;
  border-radius: 50%;
}
.btn {
  display: inline-block;
  border: none;
  margin: 0;
  padding: 0;
  font-size: 1rem;
  line-height: 1;
  background: transparent;
  -webkit-appearance: none;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: $bg-off-white;
  box-shadow: inset 0 5px 0 $shadow-inset;
}
.rock {
  background-image: $bg-rock;
  box-shadow: 0 6px 0 $shadow-rock;
}
.paper {
  background-image: $bg-paper;
  box-shadow: 0 6px 0 $shadow-paper;
}
.scissors {
  background-image: $bg-scissors;
  box-shadow: 0 6px 0 $shadow-scissors;
}
</style>

<script>
export default {
  props: ['value'],
  computed: {
    computedClass: function() {
      if (this.value === 'rock') {
        return true;
      }
      return false;
    }
  }
};
</script>
