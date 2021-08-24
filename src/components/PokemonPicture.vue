<template>
<div>
  <div class="pokemon-container">
     <img class="hidden-pokemon" :src="imgSrc"> 
    <!-- <img  class= "fade-in" :src="imgSrc" alt="pokemon"> -->
</div>
   
    
</div>   

</template>

<script>
export default {
  props:{
    pokemonId:{
        type: Number,
        required:true
    }
    

  },

  computed:{
    imgSrc(){
      return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${this.pokemonId}.svg`
    }
  }  

}
</script>

<style scoped>
/* Pokemon Picture */
.pokemon-container {
    height: 200px;
}
img {
    height: 200px;
    position: absolute;
    right: 32%;
    user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
}
.hidden-pokemon {
    filter: brightness(0);
}




</style>