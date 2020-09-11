<template>
  <div class="">
    <button
      @click="setPlayerChoice(this.value)"
      value="rock"
      v-on:click="setPlayerChoice"
    >
      rock
    </button>
    <button
      value="paper"
      @click="setPlayerChoice(this.value)"
      v-on:click="setPlayerChoice"
    >
      paper
    </button>
    <button
      value="scissors"
      @click="setPlayerChoice(this.value)"
      v-on:click="setPlayerChoice"
    >
      scissors
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    setPlayerChoice(choice) {
      this.$emit('setPlayerChoice', choice);
    }
  }
};
</script>
