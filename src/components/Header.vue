<template>
    <header class="justify-content-between">

        <img class="logo" src="../assets/img/spotify.png" alt="">
        
        <div class="pt-3 pe-5">
            <!-- <div class="input-group mb-3">
                <input type="text" class="form-control" placeholder="Search genre" aria-label="Search genre" aria-describedby="basic-addon2" v-model="searchInput" @keyup.enter="$emit('searchGenre', searchInput)">
                <div class="input-group-append">
                    <button class="btn btn-outline-secondary" @click="$emit('searchGenre', searchInput)" type="button">Button</button>
                </div>
            </div> -->
            <div class="input-group">
                <select class="custom-select" @change="onChange($event)"  id="inputGroupSelect04">
                    <option selected>Choose...</option>
                    <option value="">All</option>
                    <option value="Rock">Rock</option>
                    <option value="Jazz">Jazz</option>
                    <option value="Metal">Metal</option>
                    <option value="Pop">Pop</option>
                </select>
                <div class="input-group-append">
                    <button class="btn btn-outline-secondary" @click="$emit('searchGenre', searchInput)" type="button">Button</button>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "HeaderSpotify",
    data: function() {
        return {
            searchInput: "",
            onChange(e) {
                this.searchInput = e.target.value;
                console.log(this.searchInput);
            }
        }
    }
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