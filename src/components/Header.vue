<template>
  <header class="header">
    <div class="logo-layout">
      <img class="logo" src="../assets/logo.svg" alt="" />
    </div>
    <div class="score-box">
      <h2 class="label">SCORE</h2>
      <p class="score">{{ score }}</p>
    </div>
  </header>
</template>

<script>
export default {
  props: ['score']
};
</script>

<style lang="scss" scoped>
@import '../styles/styles.scss';
.header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  border: solid 2px $header-outline;
  padding: 0.75rem;
  height: 96px;
  .logo-layout {
    padding: 0.75rem;
  }
  .logo {
    width: 100%;
    height: 100%;
    object-fit: contain;
    object-position: 0;
  }
  .score-box {
    display: flex;
    padding: 10px;
    flex-direction: column;
    width: 80px;
    border-radius: 0.25rem;
    background-color: white;
    > * {
      text-align: center;
      margin: 0;
      line-height: 1;
    }
    .label {
      font-size: 10px;
      letter-spacing: 0.1rem;
      color: $text-blue;
    }
    .score {
      font-size: 40px;
      margin: 0;
      color: $text-dark;
      font-weight: bold;
    }
  }
}
</style>
