<template>
    <li>
        {{beer.name}}
    </li>
</template>

<script>
export default {
    name: 'favourite-beer-list-item',
    props: ['beer']

}
</script>

<style>

</style>