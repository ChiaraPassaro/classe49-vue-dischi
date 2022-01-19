<template>
  <div id="app">
    <Header
      :genres="genresList"
      @changeGenre="setGenre($event)"
    />
    <Main
      :genre="selectValue"
      @genresStart="setGenresList($event)"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      selectValue: '',
      genresList: [],
    };
  },
  methods: {
    setGenre(value) {
      this.selectValue = value;
    },
    setGenresList(value) {
      this.genresList = value;
    },
  },
};
</script>

<style lang="scss">
@import './assets/scss/style.scss';
</style>
