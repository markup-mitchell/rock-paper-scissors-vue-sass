<template>
  <div id="app">
    <Layout>
      <template #header>
        <Header :score="score"></Header>
      </template>
      <div v-if="playerChoice === 'pending'">
        <PlayerChoose @setPlayerChoice="setPlayerChoice" />
      </div>
      <div v-else>
        <template>
          <p>you chose {{ playerChoice }}</p>
          <p>the house chose {{ houseChoice }}</p>
        </template>
        <div v-if="outcome">
          {{ outcome }}
          <button v-on:click="playerChoice = 'pending'">play again</button>
        </div>
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
      score: 0,
      outcome: null
    };
  },
  methods: {
    incrementScore() {
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
      this.setOutcome();
    },
    setOutcome() {
      switch (true) {
        case this.playerChoice === this.houseChoice:
          this.outcome = 'DRAW';
          break;
        case (this.playerChoice === 'rock' &&
          this.houseChoice === 'scissors') ||
          (this.playerChoice === 'paper' && this.houseChoice === 'rock') ||
          (this.playerChoice === 'scissors' && this.houseChoice === 'paper'):
          this.outcome = 'YOU WIN';
          this.incrementScore();
          break;
        case (this.playerChoice === 'rock' && this.houseChoice === 'paper') ||
          (this.playerChoice === 'paper' && this.houseChoice === 'scissors') ||
          (this.playerChoice === 'scissors' && this.houseChoice === 'rock'):
          this.outcome = 'YOU LOSE';
          break;
        default:
          this.outcome = 'error';
          break;
      }
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
    color: white;
    button {
      background-color: transparent;
    }
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
