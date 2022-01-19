<template>
  <main class="container mt-5">
    <div
      class="row row-cols-5"
    >
      <Card
        v-for="(disc, index) in filterDiscs"
        :key="index"
        :src-image="disc.poster"
        :alt-image="disc.title"
        :title="disc.title"
        :subtitle="disc.author"
        :small="disc.year"
      />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
  },
  props: {
    genre: {
      type: String,
    },
  },
  data() {
    return {
      discs: [],
      genres: [],
      query: 'https://flynn.boolean.careers/exercises/api/array/music',
    };
  },
  computed: {
    filterDiscs() {
      if (this.genre === '') {
        return this.discs;
      }
      return this.discs.filter((element) => element.genre === this.genre);
    },
  },
  created() {
    // https://flynn.boolean.careers/exercises/api/array/music
    axios.get(this.query)
      .then((result) => {
        this.discs = result.data.response;

        this.discs.forEach((element) => {
          if (!this.genres.includes(element.genre)) {
            this.genres.push(element.genre);
          }
        });

        this.$emit('genresStart', this.genres);
      })
      .catch((error) => console.log(error));
  },
  methods: {
  //   filterDiscs() {
  //     if (this.genre === '') {
  //       return this.discs;
  //     }
  //     return this.discs.filter((element) => element.genre === this.genre);
  //   },
  },
};
</script>

<style>

</style>
