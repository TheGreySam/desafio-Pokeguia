<template>
  <div id="app">
    <img class="logo" src="/assets/pokemon-logo.jpg">
    <h1>PokeGuía</h1>

    <div>
      <label for="">Nombre:</label>
      <input type="text" v-model="nombreDelPokemon" />
      <button>Buscar</button>
    </div>
    
  </div>
</template>

<script>


export default {
  name: 'App',
  data: () => ({
    nombreDelPokemon: "",
    dataPokemon: [],
  }),
//  created() {
//    this.
//  }
//  methods: {
//    clickBotonBuscar() {
//      console.log("nombre del pokemon => ", this.nombreDelPokemon);
//    },
//    infoPikachu() {
//      fetch("https://pokeapi.co/api/v2/pokemon/nombre_pokemon")
//      .then((response) => {
//        return response.json();
//      })
//      .then((json) => {
//
//      })
//    },
//    infoPokemon() {
//      fetch(https/$this.clickBotonBuscar) {
//        .then((response))
//      }
//    }
//
//  },
}
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
</style>
