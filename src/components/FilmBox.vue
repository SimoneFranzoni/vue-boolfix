<template>
    <div>
        <h3>{{item.title}}</h3>
        <img 
        :src="'https://image.tmdb.org/t/p/w342/${item.poster_path}'" 
        :alt="item. title">
        <p>{{item.original_title}}</p>
        <div>{{item.original_language}}
           
        </div>
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
    name:'FilmBox',
    props:{
        item: Object
    },

    data(){
        return{
            flags: ['it','en']
        }
    }    
}
</script>

<style lang="scss" scoped>

@import '~@fortawesome/fontawesome-free/css/all.min.css';

/*
 <img 
    v-if="flags.include(item.original_language)"
    :src="require('../assets/img/${item.original_language}.png')" 
    :alt="item.title">
    <p v-else>Lingua: {{item.original_language}}</p>
*/
</style>