<template>
  <div id="app">
    <h1>Welcome to the Dice Roller</h1>
    <div class="container">
      <button v-on:click="rollDice(3)">Roll a D3</button>
      <button v-on:click="rollDice(4)">Roll a D4</button>
      <button v-on:click="rollDice(6)">Roll a D6</button>
      <button v-on:click="rollDice(10)">Roll a D10</button>
      <button v-on:click="rollDice(20)">Roll a D20</button>
    </div>  
    <hr>
    <br />
    <p>{{diceType}}</p>
    <p>Result: {{result}}</p>
    </div>
</template>

<script>
export default {
  name: 'app',
  data: function() {
    return { result: '',
             diceType: '' 
           }
  },
  methods: {
    rollDice: function (max) {
      this.diceType = 'Rolling a D' + max + '!';
      this.result = Math.floor(Math.random() * Math.floor(max)) + 1;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
}
button {
  padding: 25px;
  border-radius: 5px;
  margin: 0 10px;
}
.container {
  flex: 1 1 100%;
}
</style>
