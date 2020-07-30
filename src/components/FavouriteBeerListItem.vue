<template>
    <div>
        <li class="favourite-list-item">
            {{beer.name}}
        </li>
        <button v-on:click="removeFavourite">Remove</button>
    </div>
</template>

<script>
import { eventBus } from "@/main.js"
export default {
    name: 'favourite-beer-list-item',
    props: ['beer'],
    
    methods: {
        removeFavourite() {
            eventBus.$emit('beer', this.beer)
        }
    }

}
</script>

<style>

.favourite-list-item {
    display: inline-block;
    margin: 10px;
}

</style>