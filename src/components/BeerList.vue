<template>
  <div class="list-container">
      <ul>
          <beer-list-item v-for="(beer, index) in beers" :beer="beer" :key="index" :favourites="favourites"></beer-list-item>
      </ul>
  </div>
</template>

<script>
import BeerListItem from './BeerListItem.vue'

export default {
    name: 'beer-list',
    props: ['beers', 'favourites'],
    components: {
        "beer-list-item": BeerListItem
    }
}
</script>

<style>

</style>