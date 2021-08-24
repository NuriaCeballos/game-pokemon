<template>
  <div>
      <h1>¿Quién es este pokemon?</h1>
       <PokemonPicture :pokemonId="4"/>
      <PokemonOptions/>
 
  </div>
</template>

<script>


import PokemonOptions from '@/components/PokemonOptions'
import PokemonPicture from '@/components/PokemonPicture'
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