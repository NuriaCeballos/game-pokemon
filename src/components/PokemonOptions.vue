<template>
<div class="option-container">
  <ul>
    <li v-for="pokemon in pokemons"
     :key="pokemon.id" 
     @click="$emit('selection',pokemon.id)"> 
     <!-- en este click emite un valor al padre  emit tiene dos argumentos
     el nombre el  evento que se quiere distarar y es obligatorio en el segundo mandamos
     el pokemon que ha seleccionado al hacer click que va a caer como primer argumento en el 
     selection del padre en checkAnswer-->
       
     {{  pokemon.name }}
     </li>
  </ul>
 
</div>
</template>

<script>
export default {
props: {
  pokemons:{
    type:Array,
    required: true
  }
}

}
</script>

<style scoped>
/* Pokemon Options */
ul {
    list-style-type: none;
    
}
li {
    background-color: white;
    border-radius: 5px;
    border: 1px solid rgba(0, 0, 0, 0.2);
    cursor: pointer;
    margin-bottom: 10px;
    width: 250px;
}

li:hover {
    background-color: rgba(0, 0, 0, 0.05);
}

.options-container {
    display: flex;
    justify-content: center;


}


</style>