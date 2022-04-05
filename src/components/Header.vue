<template>
    <header class="bg-dark text-white">
        <div class="d-flex justify-content-end">
            <div class="input-group mb-3 w-25 pt-4 pe-3">
                <input type="text" class="form-control" v-model.trim="stringToSearch" @keyup.enter="$emit('newSearch', stringToSearch)" placeholder="Search film" aria-label="Search film" aria-describedby="basic-addon2">
                <div class="input-group-append">
                    <button class="btn btn-outline-secondary" type="button" @click="$emit('newSearch', stringToSearch)">Search</button>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "pageHeader",
    data: function() {
        return {
            stringToSearch: "",
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";

    header{
        height: 10vh;
    }
</style>