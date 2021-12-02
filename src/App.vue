<template>
  <div>
    <Header @sendSearch="performSearch"/>
    <Main :film="film"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  
  data(){
    return{
      textToSearch: '',
      film: [],
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
      apiParams: {
        api_key: 'efad0886635868ce8279b36ffb724bcb',
        language: 'it-IT',
        query: 'fant',
      }
    }
  },

  props: {
    text: String,
  },
  
  methods: {
    performSearch(text){
      this.textToSearch = text;
      console.log(text);
    },

    getApi(){
      axios.get(this.apiUrl, {params: this.apiParams})      
      .then( r =>{
      //console.log(r);
      this.film = r.data.results;
      //console.log(this.film);
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

<style lang="scss">

@import './assets/style/generals.scss';
  
</style>
