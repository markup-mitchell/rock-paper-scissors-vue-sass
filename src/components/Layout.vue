<template>
  <div class="page-wrapper">
    <slot name="header"></slot>
    <slot name="default"></slot>
    <div class="rules-layout">
      <slot name="rules"></slot>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="scss">
.page-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 2rem;
  height: 100%;
  .rules-layout {
  }
}
</style>
