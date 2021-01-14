<template lang="html">
  <div id="favourites">
      <p>Favourite Beers</p>
        <ul>
            <list-item v-for="(favBeer, index) in favouriteBeer" :beer="favBeer" :key="index"></list-item>
        </ul>
  </div>
</template>

<script>
import ListItem from './ListItem.vue'

export default {
    name: 'favourite-beer', 
    props: ['favouriteBeer'],
    components: {
        "list-item": ListItem
    }

}
</script>

<style>

</style>