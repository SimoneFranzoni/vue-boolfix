<template>
  <div>
      <FilmBox 
        v-for="item in film"
        :key="item.id"
        :item="item"
      />
  </div>
</template>

<script>
import axios from 'axios';
import FilmBox from './FilmBox';
export default {
    name:'Main',
    components: {
        FilmBox,
    },
    props: {
        text: String,
    },

    data(){
        return{
            film: [],
        }
    },

    methods:{
        getApi(){
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: 'efad0886635868ce8279b36ffb724bcb',
                    query = text,
                } 
            })      
            .then( r =>{
                console.log(r);
                this.film = r.data.results;
                console.log(this.film);
            })
            .catch( e => {
                console.log(e);
            });
        }
    },

    mounted(){
        this.getApi();
    }
}
</script>

<style lang="scss" scoped>
    
</style>