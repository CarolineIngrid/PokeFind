<template>
  <v-app>
    <h1> POKEMON </h1>
      <v-container>
        <v-card>
          {{ pokemons }}
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
    axios.get("https://pokeapi.co/api/v2/pokemon?limit=10").then((response) => {
      this.pokemons = response.data.results;
    });
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
