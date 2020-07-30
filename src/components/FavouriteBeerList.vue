<template>
<div>
    <h2>Favourite Beers</h2>
    <ul>
        <favourite-beer-list-item v-for="(beer, index) in favourites" :beer="beer" :key="index" />
    </ul>
  </div>
</template>

<script>
import FavouriteBeerListItem from './FavouriteBeerListItem.vue'

export default {
    name: 'favourite-beer-list',
    props: ['favourites'],
    
    components: {
        'favourite-beer-list-item': FavouriteBeerListItem
    }
}
</script>

<style>

</style>