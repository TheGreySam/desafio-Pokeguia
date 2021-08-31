<template>
  <div id="app">
    <img id="logo" src="./assets/International_Pokémon_logo.svg.png">
    
    <h1>PokeGuía</h1>

    <div>
      
    </div>
    <form action="">
      <label for="">Nombre:</label>
      <input type="text" v-model="nombreDelPokemon" />
      <button>Buscar</button>
      <br>
      <h1>Movimientos</h1>
      {{movimientos}}
      <br>
      <h1>Habilidades</h1>
      {{habilidades}}
    </form>
    
  </div>
</template>

<script>
//

export default {
  name: 'App',
  data: () => ({
    nombreDelPokemon: "",
    dataPokemon: {
      movimientos: null,
      habilidades: null,
    },
  }),

  methods: {
    obtenerDataPokemon() {
      console.log(this.dataPokemon);

      this.nombreDelPokemon = ``
    }
  }
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
#logo {
  height: 150pt;
}
</style>
