<template>
    <main>
        <div class="my-container">
            <div class="d-flex justify-content-center">
                <ul class="card">
                    <li v-for="(movie, index) in movies" :key="index">
                        <h1>{{movie.title}}</h1>
                        <p>{{movie.original_language}}</p>
                        <p>{{movie.vote_avarage}}</p>
                    </li>
                </ul>
            </div>
        </div>
    </main>
</template>

<script>

export default {
    name: "pageMain",
    props : ["movies"]
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    
    main{
        height: calc(100vh - 10vh);
    }
</style>