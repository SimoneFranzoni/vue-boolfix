<template>
  <div>
      <h2>{{item.results.original_title}}</h2>
  </div>
</template>

<script>
export default {
    name:'FilmBox',
    props:{
        item: Object
    }
}
</script>

<style>

</style>