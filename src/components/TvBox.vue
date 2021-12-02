<template>
  <div>
      <h2>{{item.name}}</h2>
      <p>{{item.original_name}}</p>
      <p>{{item.original_language}}</p>
      <p>{{item.vote_average}}</p>
  </div>
</template>

<script>
export default {
    name:'TvBox',
    props:{
        item: Object
    }
}
</script>

<style>

</style>