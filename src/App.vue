<template>
  <div id="app">
    <img class="logo" src="./assets/pokemon-logo.png">
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
  }),
  methods: {
    clickBotonBuscar() {
      console.log("nombre del pokemon => ", this.nombreDelPokemon);
    },
  },
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
