<template>
    <div>
        <h2>{{item.name}}</h2>
        <img 
        :src="'https://image.tmdb.org/t/p/w342/${item.poster_path}'" 
        :alt="item. title">
        <p>{{item.original_name}}</p>
        <div>{{item.original_language}}</div>
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