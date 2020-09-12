<template>
  <div id="app">
    <Layout>
      <template #header>
        <Header :score="score"></Header>
      </template>
      <div v-if="playerChoice === 'pending'">
        <PlayerChoose @setPlayerChoice="setPlayerChoice" />
      </div>
      <template #rules>
        <button>RULES</button>
      </template>
    </Layout>
  </div>
</template>

<script>
import Layout from './components/Layout';
import Header from './components/Header';
import PlayerChoose from './components/PlayerChoose';

export default {
  name: 'App',
  data() {
    return {
      playerChoice: 'pending',
      houseChoice: 'pending',
      score: 0
    };
  },
  methods: {
    increment() {
      this.score++;
    },
    setPlayerChoice(choice) {
      this.playerChoice = choice;
      this.setHouseChoice();
    },
    setHouseChoice() {
      this.houseChoice = ['rock', 'paper', 'scissors'][
        Math.floor(Math.random() * 3)
      ];
    }
  },
  components: {
    Layout,
    Header,
    PlayerChoose
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
