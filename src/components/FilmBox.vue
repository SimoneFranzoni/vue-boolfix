<template>
    <div class="box">
        <h2>{{item.title || item.name}}</h2>
        <img 
        v-if="item.poster_path"
        :src="`https://image.tmdb.org/t/p/w342/${item.poster_path}`" 
        :alt="item.title || item.name">
        <p v-else>PLACEHOLDER</p>
        <p>{{item.original_title || item.original_name}}</p>
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

.box{
    margin: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    
}


/*
 <img 
    v-if="flags.include(item.original_language)"
    :src="require('../assets/img/${item.original_language}.png')" 
    :alt="item.title">
    <p v-else>Lingua: {{item.original_language}}</p>
*/
</style>