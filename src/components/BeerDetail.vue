<template lang="html">
    <div v-if="beer" id="BeerDetail">
    <h2>{{ beer.name }}</h2>
    <button v-on:click="handleButtonClick">Add to Favourites</button>
    <div>
      <p>abv: {{beer.abv}}</p>
      <p>Description: {{beer.description}}</p>
    </div>
        <div>
            <img :src="beer.image_url">
        </div>
  </div>
    
  
</template>

<script>
import { eventBus } from '../main.js';

export default {
    name: "beer-detail",
    props: ["beer"], 
    methods: {
      handleButtonClick(){
            eventBus.$emit('favourite-beer', this.beer)}

    }

}
</script>

<style>

</style>