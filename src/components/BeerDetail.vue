<template>
  <div v-if="beer">
      <p>{{beer}}</p>
  </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['beer']
}
</script>

<style>

</style>