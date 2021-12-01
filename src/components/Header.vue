<template>
  <header>
        <div class="searchBar">
            <input type="text" placeholder="Cerca un film o una serie tv">
            <button>
                Cerca
            </button>
        </div>
  </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style lang="scss" scoped>
    header{
        height: 100px;
        background-color: cornflowerblue;
        display: flex;
        justify-content: flex-end;
        align-content: center;
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