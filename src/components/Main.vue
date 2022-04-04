<template>
    <main>
        <div class="my-cards" v-for="(element, index) in newSearch(searchString)" :key="index">
            <SingleFilm :film="film"/>
        </div>
    </main>
</template>

<script>
import SingleFilm from "./SingleFilm.vue";

export default {
    name: "pageMain",
    components: {
        SingleFilm,
    },
    props: { "searchString": String},
    data: function() {
        return{
            filmList: null,
        }
    },
    methods: {
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