<template>
    <div>
        <h3>{{item.title}}</h3>
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


</style>