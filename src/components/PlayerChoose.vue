<template>
  <div class="">
    <button
      @click="setPlayerChoice()"
      value="rock"
      v-on:click="setPlayerChoice"
    >
      rock
    </button>
    <button
      value="paper"
      @click="setPlayerChoice()"
      v-on:click="setPlayerChoice"
    >
      paper
    </button>
    <button
      value="scissors"
      @click="setPlayerChoice()"
      v-on:click="setPlayerChoice"
    >
      scissors
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    setPlayerChoice(e) {
      this.$emit('setPlayerChoice', e.target.value);
    }
  }
};
</script>
