<template>
    <div>
        <h1>{{titleType}}</h1>
        <div class="row">
            <FilmBox 
            v-for="item in listItems"
            :key="item.id"
            :item="item"
            />
        </div>      
  </div>
</template>

<script>

import FilmBox from './FilmBox';

export default {
    name:'Main',
    components: {
        FilmBox,
    },
    props: {
        listItems: Array,
        titleType: String,
    },
   
}
</script>

<style lang="scss" scoped>
    
    .row{
        display: flex;
        flex-wrap: nowrap;
        
    }

</style>