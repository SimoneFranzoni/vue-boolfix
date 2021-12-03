<template>
  <header>
        <img src="../assets\img\boolflix-logo.png" alt="">
        <div class="searchBar">
            <input 
            v-model="textToSearch"
            @keyup.enter="$emit('sendSearch',textToSearch)"
            class="form-control" type="text" placeholder="Cerca un film o una serie tv">
            <button
            @click="$emit('sendSearch',textToSearch)">
                Cerca
            </button>
        </div>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            textToSearch: '',
        }
    },
}
</script>

<style lang="scss" scoped>
    header{
        height: 100px;
        background-color: rgb(49, 49, 49);
        display: flex;
        justify-content: space-between;
       
        .searchBar{
            height: 50%;
            width: 40%;
            padding-right: 50px;
            margin-top: 20px;
            input{
                height: 100%;
                width: 80%;
            }
            button{
                height: 100%;
                width: 20%;
            }   
        }

    }
</style>