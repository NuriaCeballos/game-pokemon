<template>
<div>
<h1 v-if="!pokemon">Espere por favor</h1>
  <div v-else>
      <h1>¿Quién es este pokémon?</h1>
       <PokemonPicture :pokemonId="pokemon.id" :showPokemon="showPokemon"/>
       <PokemonOptions :pokemons="pokemonArr"
       @selection="checkAnswer($event)"/><!-- aquí el padre esta escuchando cuando se emite selection-->
       <!-- si no se ponen los argumentos no pasa nada $event es el segundo argumento -->
 
  <h2>{{messege}}</h2>
  <button @click="newGame">
    nuevo juego</button>


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
      showPokemon: false,
      showAnswer: false,
      messege:''
     
    }
  },
    methods:{
 async mixPokemonArray(){
  this.pokemonArr = await getPokemonOptions()
  
  const rndInt = Math.floor(Math.random()*4)
  this.pokemon = this.pokemonArr [ rndInt]
  
},
checkAnswer(pokemonId){//aquí recibe el evento que es el segundo argumento que recibe
//arriba en selection el checkAnswer
this.showPokemon=true

if (pokemonId === this.pokemonId){
  this.messege = `Correcto,${this.pokemon.name}`
}else {
  this.messege = `OopSS no es ${this.pokemon.name}`
}
},
newGame(){
  
   
  console.log("va el boton")
  
}


    },
      mounted(){
        
        this.mixPokemonArray()
        
      
      }
}
</script>

<style>

</style>