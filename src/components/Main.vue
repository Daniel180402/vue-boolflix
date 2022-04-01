<template>
    <main>
        <div class="my-cards" v-for="(element, index) in newSearch(searchString)" :key="index">
            <SingleFilm :film="element"/>
        </div>
    </main>
</template>

<script>
import axios from "axios";

export default {
    name: "pageMain",
    props: { "searchString": String},
    data: function() {
        return{
            filmList: null,
        }
    },
    created: function(){
        this.getApiList();
    },
    methods: {
        getApiList(){
            axios.get("https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=" + this.searchString)
            .then((result) => {
                this.filmList = result.data.response;
                console.table(this.filmList);
            })
            .catch((error) => {
                console.error(error);
            })
        },
        newSearch(stringToSearch){
            console.log(stringToSearch);
            return this.filmList.filter(
                (element) => element.title.includes(stringToSearch)
            );
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    
    main{
        height: calc(100vh - 10vh);
    }
</style>