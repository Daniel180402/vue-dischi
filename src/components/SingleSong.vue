<template>
    <div>
        <div class="card p-3 text-white" style="width: 15rem;">
            <img class="card-img-top" :src="song.poster" alt="Card image cap">
            <div class="card-body text-center">
                <h5 class="card-title">{{ song.title }}</h5>
                <p class="card-text">{{ song.author }}</p>
                <p class="card-text fw-bold text-secondary">{{ song.year }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "SingleSong",
    props: {"song" : Object}
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/style.scss";

    .card{
        height: 380px;
        @include bg-lightGrey;
    }
</style>