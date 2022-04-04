<template>
    <div>
        <div class="card p-3 text-white" style="width: 15rem;">
            <img class="card-img-top" :src="film.poster" alt="Card image cap">
            <div class="card-body text-center">
                <h5 class="card-title">{{ film.original_title }}</h5>
                <p class="card-text">{{ film.release_date }}</p>
                <p class="card-text fw-bold text-secondary">{{ film.vote_average }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "singleFilm",
}
</script>

<style>

</style>