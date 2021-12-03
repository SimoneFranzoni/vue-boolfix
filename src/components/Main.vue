<template>
    <div>
        <h2>FILM</h2>
        <div class="row">
            <FilmBox 
            v-for="item in film"
            :key="item.id"
            :item="item"
            />
        </div>

        <h2>SERIE TV</h2>
        <div class="row">
            <TvBox 
            v-for="item in tv"
            :key="item.id"
            :item="item"
            />
        </div>
      
  </div>
</template>

<script>

import FilmBox from './FilmBox';
import TvBox from './TvBox';

export default {
    name:'Main',
    components: {
        FilmBox,
        TvBox,
    },
    props: {
        film: Array,
        tv: Array,
    },
   
}
</script>

<style lang="scss" scoped>
    
    .row{
        display: flex;
        flex-wrap: wrap;
    }

</style>