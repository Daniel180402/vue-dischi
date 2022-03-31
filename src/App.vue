<template>
  <div id="app">
    <Header @searchGenre="search"/>
    <Main :searchString="searchString"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: function(){
    return {
      searchString: "",
    }
  },
  methods: {
    search(stringSearch){
      console.log(stringSearch);
      this.searchString = stringSearch;
    }
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
@import "@/style/main-style.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
