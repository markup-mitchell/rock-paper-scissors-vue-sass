<template>
  <div id="app">
    <Layout>
      <Header :score="score"></Header>
    </Layout>
  </div>
</template>

<script>
import Layout from './components/Layout';
import Header from './components/Header';

export default {
  name: 'App',
  data() {
    return {
      playerChoice: 'pending',
      houseChoice: 'pending',
      score: 12
    };
  },
  components: {
    Layout,
    Header
  }
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Barlow+Semi+Condensed:wght@600;700&display=swap');
$bg-light: #1f3757;
$bg-dark: #131537;

body {
  margin: 0;
  position: relative;
  min-width: 100vw;
  min-height: 100vh;
  * {
    box-sizing: border-box;
    font-family: 'Barlow Semi Condensed', sans-serif;
  }
}
#app {
  overflow: hidden;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-image: radial-gradient($bg-light, $bg-dark);
}
</style>
