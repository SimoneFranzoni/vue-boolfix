<template>
  <div>
      <h2>{{item.name}}</h2>
      <p>{{item.original_name}}</p>
      <p>{{item.original_language}}</p>
      <div>
            <i
            v-for="(intem, index) in 5"
            :key="index"
            class = "fa-star"
            :class="index < Math.round(item.vote_average/2) ? 'fas' : 'far'"
            >
            </i>
        </div>
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