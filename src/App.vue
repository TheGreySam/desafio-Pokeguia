<template>
  <div id="app">
    <img id="logo" src="./assets/International_Pokémon_logo.svg.png">
    
    <h1>PokeGuía</h1>

    <div>
      
    </div>
    <form @submit.prevent="nombreDelPokemon">
      <label for="">Nombre:</label>
      <input type="text" v-model="nombreDelPokemon" />
      <button @click="clickBuscador()">Buscar</button>
      <br>
      <img :src="imgPokemon" alt="imagen">
      {{dataPokemon.id}}
      
      {{pokemonApi}}
      <h1>Movimientos</h1>
      
      {{dataPokemon.moves}}
      {{dataPokemon.movimientos}}
      <br>
      <h1>Habilidades</h1>
      {{dataPokemon.abilities}}
    </form>
    
  </div>
</template>


<script>

export default {
  name: 'App',
  data: () => ({
    nombreDelPokemon: "pikachu",
    dataPokemon: {
      id: null,
      sprites: null,
      moves: null,
      abilities: null,
            
//      imgPokemon: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/25.png",
//      movimientos: null,
//      habilidades: null,
    },
    computed: {
      imgPokemon() {
        this.imgPokemon = `http://pokeapi.co/api/v1/pokemon/${this.dataPokemon.id}.png`
      }
    }
    
  }),
  methods: {
    clickBuscador() {
      this.pokemonApi()
      console.log(this.dataPokemon);
//      this.dataPokemon.id = `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/ + ${this.dataPokemon.id} + ".png"`;
    },
    pokemonApi(){
      fetch(`https://pokeapi.co/api/v2/pokemon/${this.nombreDelPokemon}`)
      .then((response) => response.json())
      .then((json) => (this.dataPokemon = json))
    },
//    imgPokemon(){
//      return${this.dataPokemon.id}
//    }
  },
  created() {
  this.pokemonApi()
}
};


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#logo {
  height: 150pt;
}
</style>
