<template>
  <div>
      <h1>¿Quién es este pokémon?</h1>
       <PokemonPicture :pokemonId="251" :showPokemon="true"/>
       <PokemonOptions :pokemons="pokemonArr"/>
 
  </div>
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions'
import PokemonPicture from '@/components/PokemonPicture'
import getPokemonOptions from '@/helpers/getPokemonOptions.js'

console.log(getPokemonOptions(),'hola')

export default {
  
  components: {PokemonPicture,PokemonOptions},

  data(){
    return{
      pokemonArr:[]
    }
  },
    methods:{
 async mixPokemonArray(){
  this.pokemonArr = await getPokemonOptions()
  
}
    },
      mounted(){
        
        this.mixPokemonArray()
        
      
      }
}
</script>

<style>

</style>