<template>
  <v-app>
    <h1> POKEMON </h1>

    <v-responsive
      class="md-auto px-12 py-6"
      >
      <v-text-field
        label="Pesquise"
        hide-details="auto"
        solo>
      </v-text-field>
    </v-responsive>

    <v-container>
      <v-card>
        <!-- {{ pokemons }} -->
        <v-row>
        <v-col
          cols="3"
          v-for="pokemon in pokemons.slice(0,12)"
          :key="pokemon.name"
        >
        <v-card>
          <img 
          :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${get_id(
            pokemon
          )}.png`"
          :alt="pokemon.name"
          width="60%">
          
          <h2 class="text-center">{{ pokemon.name }}</h2>
          <!-- <PokemonCard :pokemon="pokemon" @clicked="show_pokemon" /> -->
        </v-card>
        
          
        </v-col>
      </v-row>
      </v-card>

    </v-container>

  </v-app>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',

  components: {},

  // data: () => ({
  //   //
  // }),
  data(){
    return{
      pokemons: []
    }
  },

  mounted (){
    axios.get("https://pokeapi.co/api/v2/pokemon?limit=100000&offset=0").then((response) => {
      this.pokemons = response.data.results;
    });
  },
  methods: {
    get_id(pokemon){
      return pokemon.url.split("/")[6];
    }
  },
};
</script>

<style>
#app{
  background: #e7e7ac;
	background: linear-gradient(to right, rgb(214, 197, 236), rgb(160, 203, 230));
	color: white;
	margin: 0;
	/* font-family: rubik; **decidir depois a fonte*/
}

/* ---------- TIPOGRAFIA --------- */
h1{
  color: yellow;
  -webkit-text-stroke: 2px #000;
}
</style>
