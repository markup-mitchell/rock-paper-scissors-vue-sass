<template>
  <div id="app">
    <Layout>
      <Header></Header>
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
      houseChoice: 'pending'
    };
  },
  components: {
    Layout,
    Header
  }
};
</script>

<style lang="scss">
$bg-light: #1f3757;
$bg-dark: #131537;

body {
  margin: 0;
  position: relative;
  min-width: 100vw;
  min-height: 100vh;
  * {
    box-sizing: border-box;
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
