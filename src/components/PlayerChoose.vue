<template>
  <div class="options">
    <IconButton value="rock" />
    <IconButton value="paper" />
    <IconButton value="scissors" />
  </div>
</template>

<style>
.options {
  display: flex;
}
</style>

<script>
import IconButton from './IconButton';
export default {
  components: {
    IconButton
  }
};
</script>
