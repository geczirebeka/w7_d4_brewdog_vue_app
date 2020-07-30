<template>
  <div>
    <li v-on:click="handleClick" class="beer-list-item">
        {{beer.name}}
    </li>
    <button v-if="!favourites.includes(beer)"  v-on:click="addFavourite">Favourite</button>
  </div>
</template>

<script>
import { eventBus } from '@/main.js'

export default {
    name: 'beer-list-item',
    props: ['beer', 'favourites'],
    
    methods: {
        handleClick() {
            eventBus.$emit('selected-beer', this.beer)
        },
        addFavourite() {
            eventBus.$emit('favourites', this.beer)
        }
    }

}
</script>

<style scoped>

.beer-list-item {
    display: inline-block;
    margin: 10px;
}

</style>