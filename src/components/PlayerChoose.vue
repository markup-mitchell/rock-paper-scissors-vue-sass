<template>
  <div class="">
    <IconButton
      value="rock"
      @click="setPlayerChoice()"
      v-on:click="setPlayerChoice"
    />
    <IconButton
      value="paper"
      @click="setPlayerChoice()"
      v-on:click="setPlayerChoice"
    />
    <IconButton
      value="scissors"
      @click="setPlayerChoice()"
      v-on:click="setPlayerChoice"
    />
  </div>
</template>

<script>
import IconButton from './IconButton';
export default {
  methods: {
    setPlayerChoice(e) {
      this.$emit('setPlayerChoice', e.target.value);
    }
  },
  components: {
    IconButton
  }
};
</script>
