<template>
    <main>
        <div class="my-container">
            <div class="my-wrapper">
                <div class="my-cards" v-for="(element, index) in newSearch(searchString)" :key="index">
                    <SingleSong :song="element"/>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import axios from "axios";

import SingleSong from './SingleSong.vue'

export default {
    name: "MainPage",
    props: { "searchString": String},
    components: {
        SingleSong
    },
    data: function() {
        return{
            songList: null
        }
    },
    created: function(){
        this.getApiList();
    },
    methods: {
        getApiList(){
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((result) => {
                this.songList = result.data.response;
                console.table(this.songList);
            })
            .catch((error) => {
                console.error(error);
            })
        },
        newSearch(stringToSearch){
            console.log(stringToSearch);
            return this.songList.filter(
                (element) => element.genre.includes(stringToSearch)
            );
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";

    main{
        height: calc(100vh - 10vh);
        background-color: $darkGrey;
        display: flex;
        align-items: center;

        .my-wrapper{
            width: 100%;
            display: flex;
            flex-wrap: wrap;

            .my-cards{
                width: calc(100% / 5);
                margin-bottom: 1rem;
            }
        }
    }
</style>