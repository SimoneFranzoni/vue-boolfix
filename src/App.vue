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
        query: '',
      }
    }
  },

  props: {
    text: String,
  },
  
  methods: {

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
    },

    performSearch(text){
      this.apiParams.query = text;
      console.log(this.apiParams.query);
      //modifico il dato ed eseguo nuovamente la chimata
      this.getApi()
    },
  },

  mounted(){
    this.getApi();
  }
}

</script>

<style lang="scss">

@import './assets/style/generals.scss';
  
</style>
