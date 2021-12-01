<template>
  <div>
    <Header @sendSearch="performSearch"/>
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  
  data(){
    return{
      textToSearch: '',
    }
  },

  props: {
    text: String,
  },
  
  methods: {
    performSearch(text){
      this.textToSearch = text;
      console.log(this.textToSearch);
      console.log(text);
    },
  }
}

</script>

<style lang="scss">

@import './assets/style/generals.scss';
  
</style>
