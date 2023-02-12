<template>
  <v-app>
    <h1> POKEMON </h1>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    //
  }),
};
</script>

<style>
#app{
  background: #e7e7ac;
	background: linear-gradient(to right, rgb(214, 197, 236), rgb(160, 203, 230));
	color: white;
	margin: 0;
	/* font-family: rubik; */
}

/* ---------- TIPOGRAFIA --------- */
h1{
  color: yellow;
  -webkit-text-stroke: 2px #000;
}
</style>
