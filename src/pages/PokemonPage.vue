<template>
  <div>
      <h1>¿Quién es este pokémon?</h1>
       <PokemonPicture :pokemonId="4" :showPokemon="true"/>
      <PokemonOptions/>
 
  </div>
</template>

<script>

import getPokemonOptions from '@/helpers/getPokemonOptions'
import PokemonOptions from '@/components/PokemonOptions'

import PokemonPicture from '@/components/PokemonPicture'

console.log(getPokemonOptions())

export default {
  name: 'PokemonPage',
  components: { 
    PokemonPicture,
    PokemonOptions
    
  }
}
</script>

<style>

</style>