<template>
  <header class="header">
    <div class="logo-layout">
      <img class="logo" src="../assets/logo.svg" alt="" />
    </div>
    <div class="score-box">
      <h2 class="label">SCORE</h2>
      <p class="score">12</p>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  border: solid 2px rgba(255, 255, 255, 0.5);
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
      font-family: sans-serif;
      margin: 0;
    }
    .label {
      font-size: 10px;
    }
    .score {
      font-size: 40px;
      margin: 0;
    }
  }
}
</style>
