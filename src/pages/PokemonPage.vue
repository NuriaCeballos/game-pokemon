<template>
<div>
<h1 v-if="!pokemon">Espere por favor</h1>
  <div v-else>
      <h1>¿Quién es este pokémon?</h1>
       <PokemonPicture :pokemonId="pokemon.id" :showPokemon="showPokemon"/>
       <PokemonOptions :pokemons="pokemonArr"
       @selection="checkAnswer"/><!-- aquí el padre esta escuchando cuando se emite selection-->
 
  </div>
  </div>
  
  
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions'
import PokemonPicture from '@/components/PokemonPicture'
import getPokemonOptions from '@/helpers/getPokemonOptions.js'



export default {
  
  components: {PokemonPicture,PokemonOptions},

  data(){
    return{
      pokemonArr:[],
      pokemon:null,
      showPokemon: false
     
    }
  },
    methods:{
 async mixPokemonArray(){
  this.pokemonArr = await getPokemonOptions()
  
  const rndInt = Math.floor(Math.random()*4)
  this.pokemon = this.pokemonArr [ rndInt]
  console.log(rndInt)
  
},
checkAnswer(){

  console.log('Pokemosn Page llamado');

}

    },
      mounted(){
        
        this.mixPokemonArray()
        
      
      }
}
</script>

<style>

</style>