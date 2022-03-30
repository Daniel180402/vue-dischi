<template>
    <header>
        <img class="logo" src="../assets/img/spotify.png" alt="">
    </header>
</template>

<script>
export default {
    name: "HeaderSpotify"
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/style.scss";

    header{
        height: 10vh;
        background-color: $lightGrey;
        display: flex;
        align-items: center;

        .logo{
            height: 60%;
            padding-left: 1rem;
        }
    }
</style>