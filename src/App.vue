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
      
      <img :src="imgPokemon" class="img" alt="imagen">
      
      
      <h1>Nombre</h1>
      
       {{nombre}}

      
      
      <h1>Movimientos</h1>
      <li v-for="(movimiento, index) in movimientos" 
      :key="index"
      v-text="movimiento.move.name">
        

      </li>
      <div>
        

      </div>
      
      <br>
      <h1>Habilidades</h1>
      <li v-for="(habilidad, index) in habilidades" 
      :key="index"
      v-text="habilidad.ability.name">
      </li>
      
    </form>
    
  </div>
</template>


<script>


export default {
  name: 'App',
  data: () => ({
    nombreDelPokemon: "pikachu",
    
    dataPokemon: "",
      id: "",
      sprites: {
        other: {
          dream_world: {
            front_default: "",
          }
        }
      },
//      moves: {
//        nombre: ""
//        },
      abilities: [],
//      front_default: "",
//      species: "",    
//      other: "",
//      dreamworld: "",
//      move: [],
      moves: [],
//      ability: ""
   
//    },
          
  }),
  
  computed: {

    nombre() {
      return  this.dataPokemon.name;
    },
    imgPokemon() {
//      return this.dataPokemon.sprites.other.dream_world.front_default 
//     return this.dataPokemon.sprites.front_default
//      return this.dataPokemon.id
      return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/${this.dataPokemon.id}.png`

    },
    movimientos() {
      return this.dataPokemon.moves;
        
      
    },
    habilidades() {
      return this.dataPokemon.abilities;
    }
  },
  
  methods: {
    clickBuscador() {
      this.pokemonApi()
      console.log(this.dataPokemon);

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
.img {
  height: 150pt;
}
</style>
