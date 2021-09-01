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
      <img :src="dataPokemon.sprites.front_default" alt="imagen">
      {{dataPokemon.id}}
      {{dataPokemon.sprites.front_default}}

      
      
      <h1>Movimientos</h1>
      
      {{}}
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
      front_default: null,
      species: null,
            
//      imgPokemon: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/25.png",
//      movimientos: null,
//      habilidades: null,
    },
    
    
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
  },

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
