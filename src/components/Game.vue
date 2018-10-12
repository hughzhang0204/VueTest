<template>
  <div class="game">

    <h3>Game List</h3>
    <div v-if="seen">2017 New Games</div>
    <div>
      <ul>
        <li v-for="(game,id) in games" :key="id">
          {{game.title}} / A$ {{game.price}}
        </li>
      </ul>
    </div>

    <div style="margin-top: 20px">
      <p>Your favourite game: {{myGame}}</p>
      <input v-model="myGame"/>
    </div>
<!-- v-on (keydown, keyup, click, dbclick, load, etd.)-->
    <div>
      <button v-on:click="btnClick('FIFA')">FIFA Soccer 2019</button>
      <button v-on:click="btnClick('Spider Man')">Spider-Man</button>
      <button @click="btnClick('God War')">God of War</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'game',
  data: function () {
    return {
      seen: true,
      games: [
        {id: 0, title: 'FIFA Soccer 2019', price: 400},
        {id: 1, title: 'Spider-Man', price: 500},
        {id: 2, title: 'God of War', price: 600}
      ],
      myGame: 'Super Mario',
      method: {
        btnClick: function (pname) {
          this.$emit('click')
        }
      }

    }
  }
}
</script>

<style scoped>
  .game{
    text-align: center;
  }
</style>
