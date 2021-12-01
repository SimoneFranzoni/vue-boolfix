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

    data(){
        return{
           apiUrl: 'https://api.themoviedb.org/3/movie/550?api_key=efad0886635868ce8279b36ffb724bcb',
        }
    },

    methods:{
        getApi(){
            axios.get(this.apiUrl)
            .then( r =>{
                this.film = r.data;
            })
            .catch( e => {
                console.log(e);
            })
        }
    },

    mounted(){
        this.getApi();
    }
}
</script>

<style >

</style>