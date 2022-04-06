<template>
    <main>
        <div class="my-container">
            <div class="d-flex flex-wrap justify-content-center mt-5">
                <div class="card m-2" style="width: 18rem;" v-for="(movie, index) in movies" :key="index">
                    <img class="card-img-top" :src="'https://image.tmdb.org/t/p/w342/' + movie.poster_path" alt="No image available">
                    <div class="card-body d-flex justify-content-center flex-column align-items-center">
                        <h5 class="card-title">{{ movie.title }}  {{ movie.name }}</h5>
                        <p class="card-text"> {{ movie.original_language }} </p>
                        <p> {{movie.vote_average}} </p>
                        <p> {{movie.release_date}} {{ movie.first_air_date }}</p>
                    </div>
                </div>
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

        .card{
            width: calc(100% / 4);

            .card-img-top{
                min-height: 300px;
            }
        }
    }
</style>