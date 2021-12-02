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

import FilmBox from './FilmBox';
export default {
    name:'Main',
    components: {
        FilmBox,
    },
    props: {
        film: Array,
    },
   
}
</script>

<style lang="scss" scoped>
    
</style>